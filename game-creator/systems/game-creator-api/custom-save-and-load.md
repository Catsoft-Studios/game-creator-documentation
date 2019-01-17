# Custom Save & Load

Game Creator has a built-in functionality for saving and loading games. For non-programmers this should be as easy as using the **Load Game** Action to load a previously saved game and the **Save Game** Action for saving it.

Despite this, the save/load system has some constraints and it is nearly impossible to cover all cases with one generic script. That's why we've exposed the Save/Load API in case you want to create a custom savable object.

Here we'll cover all the necessary steps you need to take when creating an extension of **Game Creator** or you simply want to use its save/load features with some custom scripts.

{% hint style="info" %}
We've tried to keep the Save/Load manager as simple as possible. If you have a better idea of how to handle this, we're open to discuss the implementation.
{% endhint %}

## The IGameSave Interface

Game Creator has a manager class that handles loading and saving the game. All that it needs is to know what objects should be loaded and which data from which objects should it save.

We inform the **SaveLoadManager** about these aspects using the **`IGameSave`** interface implementing the following methods.

```csharp
public interface IGameSave
{
	string GetUniqueName();
	
	object GetSaveData();
	System.Type GetSaveDataType();
	
	void ResetData();
    void OnLoad(object generic);
}
```

### GetUniqueName

As its name implies, you should return a unique name which will be used to identify this object. You can use something as simple as `"my-data"`.

### GetSaveData

The data that will be saved. For example, you can use the `MyData` class to return which data should be saved.

```csharp
[System.Serializable]
public class MyData
{
    public string name = "Game Creator";
    public int age = 2;
}
```

{% hint style="warning" %}
The returned data object should be from a **serializable** type.
{% endhint %}

### GetSavedDataType

The type of the GetSaveData method. For example, following our previous example, if your saved data was an object of type **`MyData`**, the implementation of this method would be.

```csharp
public System.Type GetSaveDataType()
{
	return typeof(MyData);
}
```

### ResetData

This method will be called right before loading a game. It allows to reset the state of your game to its default values, in case the player was playing from another loaded game.

{% hint style="info" %}
In most cases it will be as easy as creating an empty instance of the **MyData** class.
{% endhint %}

### OnLoad

This is where the magic happens. When the player loads a game this method will be called with a generic object as a parameter. You'll need to explicitly cast the generic object to a usable one and rebuild the state from its parameters.

```csharp
public void OnLoad(System.Object generic)
{
	this.myData = (MyData)generic;
}
```

## Initialization

It is important to know that whenever an object that implements the `IGameSave` interface it needs to inform the SaveLoadManager that a new savable/loadable object has been created.

The easiest way to do this is inside the `Start()` method:

```csharp
void Start()
{
    SaveLoadManager.Instance.Initialize(this);
}
```

## Complete Example

To better illustrate how to use the Save/Load system let's see a simple yet complete example. Imagine our game always has some music track playing in the background as well as at a user defined volume level. The class that manages this part of the game could be named as **`BackgroundMusicManager`**.

{% code-tabs %}
{% code-tabs-item title="BackgroundMusicManager.cs" %}
```csharp
public class BackgroundMusicManager : MonoBehaviour
{
    public string songName = "Dream On";
    public float volume = 1.0f;
    
    void Start()
    {
        this.PlaySong();
    }
    
    private void PlaySong()
    {
        // loads the audio clip with name this.songName 
        // and plays it with the volume this.volume
    }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

A simple and straightforward component, right? Let's modify it so it supports Game Creator Save/Load system.

We need to make the **`BackgroundMusicManager`** inherit from the **`IGameSave`** interface and implement all its methods. After that we'll also have to add the initialization line inside the **`Start()`** method.

We'll also need to create a class to save both the current song name and the volume and set it as serializable. You can do this on a separate file, though we prefer to create an internal class.

{% code-tabs %}
{% code-tabs-item title="BackgroundMusicManager.cs" %}
```csharp
public class BackgroundMusicManager : MonoBehaviour, IGameSave
{
	// Create a serializable class which contains
	// all savable data:
	[System.Serializable]
	public class MusicData
	{
		public string songName = "Dream On";
	    public float volume = 1.0f;
	}
    
    // (Optional) Replace the individual 
    // properties for a savable class instance:
    public MusicData musicData = new MusicData();
    
    void Start()
    {
        this.PlaySong();
        
        // Notify the SaveLoadManager that a new
        // instance of a savable/loadable object
        // has been created.
        SaveLoadManager.Instance.Initialize(this);
    }
    
    private void PlaySong() { ... }
    
    // implement the IGameSave interface:
    
    public string GetUniqueName()
	{
		return "background-music";
	}

	public System.Type GetSaveDataType()
	{
		return typeof(MusicData);
	}

	public System.Object GetSaveData()
	{
		return this.musicData;
	}

	public void ResetData()
	{
		this.musicData = new MusicData();
	}

	public void OnLoad(System.Object generic)
	{
		MusicData loadedMusicData = (MusicData)generic;
		this.musicData = loadedMusicData;
	}
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

And _voilá!_ That's all that needs to be done. Of course this is a simple example but unless you want to save procedural data with multiple instances it should be pretty straight forward and similar to this example.

## Scene Objects

Sometimes you will not only want to save Singleton objects but also individual scene objects. In these cases you have to take into account a couple of things.

The first one is that the GetUniqueName method should return a unique project name. Two objects with the same name in two different scenes will overwrite each other. 

{% hint style="success" %}
One way of solving this problem is assigning a unique generic value using the **GUID** class.
{% endhint %}

The other issue is the edge case where whether you want to keep changes when switching between scenes without loading the game. To explain this, consider the following example:

1. Player is in **scene A** and pulls the **lever L**.
2. Player goes to **scene B** and **saves** the game.
3. Player goes to **scene A**

Should the Lever L be pulled? That's something you should consider. Most cases will be positive, but other times you'll want to reset the changes \(for example, having enemies repopulate the field\).

To keep the changes all you need to do is to inform the **`SaveLoadManager`** class that the object has been destroyed \(when switching between scenes\) and it will automatically restore the state when going back.

{% code-tabs %}
{% code-tabs-item title="MyClass.cs" %}
```csharp
public class MyClass : MonoBehaviour, IGameSave
{
    // (...)
    
    void OnDestroy()
    {
        SaveLoadManager.Instance.OnDestroyIGameSave(this);
    }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}


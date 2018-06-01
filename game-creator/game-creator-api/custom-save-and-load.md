---
description: Snake? Snake?! Snaaaaaaake!!!
---

# Custom Save & Load

Game Creator has a built-in functionality for saving and loading games. For non-programmers this should be as easy as use the **Load Game** to load a previously saved game and **Save Game** for saving it.

For programmers, the save/load system has so many constraints that it is nearly impossible to cover all cases with one generic script.

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

## Example




# Variables Access

Accessing variables is done though the `VariablesManager` static class.

{% hint style="info" %}
To use it make sure you include the namespace `GameCreator.Variables`.
{% endhint %}

Variables follow a very simple convention. Accessing global variables is done through the `GetGlobal` and `SetGlobal` static methods. Homonymously, accessing local variables is done through the `GetLocal` and `SetLocal` methods.

## Global Variables

Global Variables have a wide application scope and their values are shared between all scenes.

### Get Global Variables

Accessing a global variable can be done specifying the return type or by requesting a generic object and later explicitly casting it to a usable type.

{% hint style="success" %}
Despite having two methods for getting and setting global variables, it's highly recommended  explicitly specifying the type. Otherwise casting errors might arise.
{% endhint %}

```csharp
public static object GetGlobal(string name)
```

### Set Global Variables

Setting a global variable value also very easy.

```csharp
public static void SetGlobal(string name, object value)
```

### Exist Global Variables

You can also check if a global variable has been defined.

```csharp
public static bool ExistsGlobal(string name)
```

## Local Variables

Local variables pretty much work the same way as global variables. The difference is that they need a target object from where to start looking for the variable's value.

### Get Local Variables

If the `inChildren` property is set to `true`, then the variable will be depth-search through the `target` game object and its children.

{% hint style="warning" %}
Depth searching through a target and its children comes at a small performance cost.
{% endhint %}

```csharp
public static object GetLocal(GameObject target, string name, bool inChildren = false)
```

### Set Local Variables

Setting a local variable value is as easy as getting them:

```csharp
public static void SetLocal(GameObject target, string name, object value, bool inChildren = false)
```

### Exist Local Variables

Checking if a local variable exists is done exactly like with global variables

```csharp
public static bool ExistsLocal(GameObject target, string name, bool inChildren = false)
```

## List Variables

**List Variables** code syntax is a bit different from the **Local** and **Global Variables**. Instead of setting or getting a single variable, you insert a variable into an array-placed collection of variables.

### Get List Variables

Get the element of a **List Variables** based on the `ListVariables.Position` enum.

```csharp
public static Variable GetListItem(ListVariables list, ListVariables.Position position, int index = 0)
```

The **`ListVariables.Position`**  enum has the following options:

* **Index:** Access by zero-based index. Requires an extra parameter with an index
* **First:** Access the first element
* **Last:** Access the last element
* **Previous:** Access the previous element based on the iterator's value
* **Current:** Access the element pointed by the iterator's value
* **Next:** Access the next element based on the iterator's value
* **Random:** Access a random position

### Set List Variables

Insert or remove an element of a **List Variables** object.

```csharp
public static void ListPush(ListVariables target, ListVariables.Position position, object value)
```

```csharp
public static void ListRemove(GameObject target, ListVariables.Position position)
```

## Examples

Here are some common examples. Let's say you have a Global Variable called **`player-score`** stored in as a **Number**. **Number** type variables are **`floats`**.

```csharp
public float GetPlayerScore()
{
    object result = VariablesManager.GetGlobal("player-score");
    return (float)result;
}
```

Notice how **`GetGlobal`** returns an **`object`**. This means that the result can be anything: from a **`float`**, a **string**, a **`Game Object`** or even **`null`**!

You have to know beforehand the type of the variable you're trying to access and use an explicit cast to transform an object into the type you want; in this case, a **`float`**.

Now let's say we want to increase the previous variable each time the player wins the game.

```csharp
public void IncreasePlayerScore()
{
    float score = this.GetPlayerScore();
    VariablesManager.SetGlobal("player-score", score + 1);
}
```

Using the previous method, we can easily get the current player's score and call the **`SetGlobal`** method to store the current score plus 1.

## TypeProperties

When integrating Game Creator with your custom scripts you'll want to make use of both constant variable values \(float, strings, ...\) and Game Creator Variables. 

This is where TypeProperties come to play. Instead of declaring a public float value so you can set up its value in the Inspector, use a NumberProperty. It will allow you to choose between a constant value, a local variable or a global variable.

This is better explained with an example. Imagine you have a script where you need to use a string value that references the player's name. You would normally write:

```csharp
public class Player : MonoBehaviour
{
    public string playerName = "John";
    
    public void Awake()
    {
        Debug.Log(playerName);
    }
}
```

And in the Inspector this component would display as a textfield where you can modify the `playerName` property.

Using TypeProperty \(`StringProperty` in this case\) you can define in edit-mode whether if `playerName` variable will use a constant value or any other Game Creator variable value.

```csharp
public class Player : MonoBehaviour
{
    public StringProperty playerName = new StringProperty("John");
    
    public void Awake()
    {
        Debug.Log(playerName.GetValue());
    }
}
```

If the user has decided to use a **constant value** `"John"` as the `playerName` value, `playerName.GetValue()` will return a string with `"John".` 

If the user uses a **Global Variable** or a **Local Variable** for `playerName`, using `playerName.GetValue()` will return the Global/Local variable's value.


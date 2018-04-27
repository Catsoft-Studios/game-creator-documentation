---
description: VariablesManager.Get()
---

# Variables Access

Accessing variables is done though the `VariablesManager` static class.

{% hint style="info" %}
To use it make sure you include the namespace `GameCreator.Variables`.
{% endhint %}

Variables follow a very simple convention. Accessing global variables is done through the `GetGlobal` and `SetGlobal` static methods. Homonimously, accessing local variables is done through the `GetLocal` and `SetLocal` methods.

## Global Variables

Global Variables have a wide application scope and their values are shared between all scenes.

### Get Global Variables

Accessing a global variable can be done specifying the return type or by requesting a generic object and later explicitly casting it to a usable type.

{% hint style="success" %}
Despite having two methods for getting and setting global variables, it's highly recommended  explicitly specifying the type. Otherwise casting errors might arise.
{% endhint %}

```csharp
public static T GetGlobal<T>(string name)
```

```csharp
public static object GetGlobal(string name)
```

### Set Global Variables

Setting a global variable value also very easy.

```csharp
public static void SetGlobal<T>(string name, T value)
```

```csharp
public static void SetGlobal(string name, object value)
```

### Exist Global Variable

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
public static T GetLocal<T>(GameObject target, string name, bool inChildren = false)
```

```csharp
public static object GetLocal(GameObject target, string name, bool inChildren = false)
```




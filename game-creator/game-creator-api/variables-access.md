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

Accessing a Global variable can be done specifying the return type or by requesting a generic object and later explicitly casting it to a usable type.

```csharp
public static T GetGlobal<T>(string name)
```

```csharp
public static object GetGlobal(string name)
```

### Set Global Variables


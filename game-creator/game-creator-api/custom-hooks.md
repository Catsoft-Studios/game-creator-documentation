---
description: HookCat.Instance
---

# Custom Hooks

Hooks are _Unity_ components that allow you to easily access unique objects such as the _Player_ or the _Main Camera_. Their use is not required but useful if you want to simplify the process of selecting common objects.

{% hint style="info" %}
Let's say you want to detect when the player enters a certain area with a **Trigger**. 

Instead of setting the **Trigger** to Enter and dragging and dropping the **Player** game object into the target field, you can simply mark the `collideWithPlayer` checkbox and it automatically looks for the **Player**.
{% endhint %}

Creating a custom hook is really easy. **Game Creator** already provides a hook for some components but if you want, for example, to create one for the player's _Dragonfly_, you can create a class that inherits from `IHook` as follows:

```csharp
public class HookDragonfly : IHook<HookDragonfly> {}
```

{% hint style="warning" %}
Notice that using **Hooks** requires to use the `GameCreator.Core.Hooks` namespace
{% endhint %}

That's all. Add this component to you game object and you'll be able to access it using `HookDragonfly.Instance`.


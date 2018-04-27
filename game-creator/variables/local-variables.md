---
description: Strength = 999
---

# Local Variables

**Local Variables** are one of the newest and most useful **Game Creator** tools. They allow to access different variable instances from different game objects but with the same name.

For example, let's say you want to give each character of your game a unique name. You can create a **Local Variables** component on each one of them and create a local variable called `name`.

When accessing it, each character will return its own unique name.

{% hint style="info" %}
**Local Variables** work pretty much like **Global Variables**. The difference is that they live inside the scope of a game object, not project wide.
{% endhint %}


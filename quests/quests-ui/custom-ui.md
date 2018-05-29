---
description: You made your quests. Now make them look yours.
---

# Custom UI

The **Quests** module comes packed with two assets: the **Journal** and the **Quests HUD**. These assets are nothing more than a combination of default Unity UI components and two Quests components.

## Quest UI Components

Every game has its own unique approach when presenting quests. Some only give you a small text about what to do next, and others may give you a full featured Quest log with history descriptions, detailed tasks and statuses.

That's why we tried to reduce all the complexity to its bare minimum and we came up with just two components:

* Quests Group
* Quest UI

With these two components \(and combining them\) you can create any quest UI.

{% hint style="info" %}
If you want to create your own **Quest UI** we highly recommend examining and learning how the **Quest Journal** and the **Quests HUD** work by inspecting their component structure.
{% endhint %}

### Quests Group

The Quests Group allows to filter by **Quest** status and instantiate a prefab per quest.

![](../../.gitbook/assets/quests-questsgroup.jpg)

Initialization has two options; automatic and Manual.

* **Automatic:** Instantiates a list of quests using the specified prefab inside the Container Rect Transform following the filter constraints as soon as it can.
* **Manual:** Does the same as the automatic but needs to be called from another component or script.

{% hint style="info" %}
The Filter allows you to specify multiple types of statuses. For example, you could display all quests that are complete or active.
{% endhint %}




---
description: Call Actions and Events
---

# Triggers

**Triggers** are used to fire **Actions** and **Events** when _something_ happens. This _something_ can range from the player pressing a certain key to an NPC's entering a certain area.

![](../../.gitbook/assets/triggers.jpg)

Triggers are executed from top to bottom. First the **Events** and then the rest of the **Actions**.

## Advanced Options

At the bottom of the component there's an **Advanced Options** foldout. You can specify a minimum distance from which the **Player** has to be for this trigger to be activated. 

{% hint style="info" %}
This is specially useful when dealing with pickup items or interactive doors.
{% endhint %}

There's also a shortcut option to create a [Hotspot](hotspots.md) component from within the **Trigger**.


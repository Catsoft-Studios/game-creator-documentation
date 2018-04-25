# Triggers

**Triggers** are used to fire **Actions** and **Events** when _something_ happens. This _something_ can range from the player pressing a certain key to an NPC's entering a certain area.

![](../../.gitbook/assets/triggers.jpg)

{% hint style="warning" %}
Triggers are executed from top to bottom. First the **Events** and then the rest of the **Actions**.
{% endhint %}

## Advanced Options

At the bottom of the component there's an **Advanced Options** foldout. You can specify a minimum distance from which the **Player** has to be for this trigger to be activated. 

{% hint style="info" %}
This is specially useful when dealing with pickup items or interactive doors.
{% endhint %}

There's also a shortcut option to create a [Hotspot](hotspots.md) component from within the **Trigger**.

## Tips

Some times you'll want a **Trigger** to execute an **Action** only once. You can easily take advantage of an **Action's** `DestroyAfterFinishing` property to destroy both the **Action** and the **Trigger**.

To do so, simply add an **Actions** component inside the same **Game Object **where the **Trigger** is. After executing the **Actions**, it will destroy the entire **Game Object**.


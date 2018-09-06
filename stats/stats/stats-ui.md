---
description: Health <3 <3 <3 <3
---

# Stats UI

What good is a **Stat** or **Attribute** if you don't display it? The **Stats** component comes back with a collection of components that makes this process a breeze.

There are 4 components in total:

* **Stat UI:** Displays current information of a **Stat** in different formats.
* **Attribute UI:** Displays current information of an **Attribute** in different formats.
* **Status Effects UI:** Shows information about all **Status Effects** of a target.
* **Status Effect UI:** Shows information about a single **Status Effect** of a target.

{% hint style="info" %}
**Status Effects UI** and **Status Effect UI** are very closely related and are usually used together.
{% endhint %}

## Stat UI & Attribute UI

**Stats UI** and **Attributes UI** are pretty much the same. They both share the common properties where you can attach a _Text_ element to display its title name and other common properties. In this section we'll cover the **Attributes UI** is exactly the same but with fewer fields:

![\(Attributes UI component\)](../../.gitbook/assets/attributes-ui.png)

We've split the component in different sections. All of them but the first two are optional and won't have any effect if left in blank.

### A. Descriptors

You can display the title, description, icon or any of the descriptor properties of a Stat or Attribute by placing the corresponding Unity UI element.

{% hint style="info" %}
Note that the **Color** property accepts both **Text** and **Image** elements.
{% endhint %}

### B. Text Values

You can use these fields to display the value of the **Stat** or **Attribute**. These values can also be formatted using the square bracket notation.

* **`{0}`** refers to the current value
* **`{1}`** refers to the maximum value \(or **Stat** value\)

###  C. Fill Image

Because an **Attribute** is a value between 0 and a maximum value, they are usually used to represent heath, mana and energy gauges. The [Fill Image](https://docs.unity3d.com/ScriptReference/UI.Image-fillAmount.html) is a special Unity property from an _Image_ component that allows to mask a percentage of its sprite based on a value between 0 and 1.

{% hint style="info" %}
You can create health bars that fill from left to right, right to left, vertical, or even circular. Check out the [Image component documentation](https://docs.unity3d.com/ScriptReference/UI.Image.html) to learn more about it. The sky is the limit!
{% endhint %}

### D. Scaling

If instead of filling an image you prefer to scale it down based on the percentage of the Attribute value versus the maximum amount you can do it here.

For example, a **`health`** **Attribute** with a value of 300 of 500 \(which equals to a 60%\) would modify the scale of the _Rect Transform_ to 0.6.

## Status Effect & Effects UI

**Status Effects** and **Status Effect UI** \(notice the extra "_s_" for the plural\) handle the display of the different **Status Effects** a game object has.

* **Status Effects UI:** Listens, creates, destroys and updates the different **Status Effect UI** children.
* **Status Effect UI:** Updates their interface values according to the current state of the status effect.

Let's go step by step. These two components are usually used in conjunction, so we'll show an example of how to show all **Status Effects** affecting a particular object.

![\(Status Effects UI component\)](../../.gitbook/assets/status-effects-ui.png)

  
First we need a Status Effects UI. This component will need a target object with a Stats component from which to query the different Status Effects. You can also choose between showing all status effects, only displaying those that are _Positive_ \(buffs\), _Negatives_ \(debuffs\) or the ones marked as _Other_.

There are two last properties: The **Container** and the **Prefab Status Effect**. The **Prefab** will be instantiated inside the **Container** as many times as **Status Effects** applied to the target object. For example, if the player has stacked two **Poison Status Effects**, the prefab will be instantiated only once.

Once this prefab is instantiated, the prefab should also have a **Status Effect UI** component, which will be initialized with the values that its parent provides.

![\(Status Effect UI component\)](../../.gitbook/assets/status-effect-ui.png)

The **Status Effect UI** behaves pretty much like the Stat UI or the Attribute UI and you can optionally fill any of the following fields:

* **Title:** The title of the Status Effect correctly localized.
* **Description:** The description of the Status Effect localized.
* **Icon:** The Image where to add the sprite of the Status Effect.
* **Color:** Text or Image that will be tinted with the color of the Status Effect.
* **Stack:** A Text component that will show the current number of stacked Status Effects of that type.

{% hint style="info" %}
Both the **Status Effect/s UI** and the **Stat/Attribute UI** components are automatically updated when a change is detected. No need to worry about that.
{% endhint %}


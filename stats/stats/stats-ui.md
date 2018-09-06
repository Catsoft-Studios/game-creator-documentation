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

**Stats UI** and **Attributes UI** are pretty much the same. The only difference is that one accepts an **Attribute** and the other one a **Stat**. Here's an example of an **Attribute UI** component:

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

 


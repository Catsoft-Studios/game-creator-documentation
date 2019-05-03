---
description: '[0][1][2][3]'
---

# List Variables

**List Variables** are similar to [Local Variables](local-variables.md) in that their scope is limited to the scene they are at. Instead of accessing the Variables by name, you can access them by **index**.

![\(List Variables example with 3 elements\)](../../../.gitbook/assets/list-variables-header.jpg)

Items can be inserted and removed at any position. They are very useful when you want to stack a bunch of game objects \(or any supported data\) and do something with them, without having to worry about how many elements you have stored.

{% hint style="success" %}
For example, you can have a SIM game where your village has multiple characters doing chores around the town. 

Each of these villagers could be assigned a position inside a List Variable called **`"citizens"`**. 

This List Variable could be used to query information such as getting the citizen that is nearest to the forest and start collecting wood, and giving birth to new citizens would be as easy as adding a new Game Object at the end of the **`"citizens"`** **List Variable**.
{% endhint %}

## Managing List Variables

List V


---
description: >-
  BE CAREFUL WITH THAT...! ... Never mind, I'll be poisoned for the next 3
  minutes...
---

# Status Effects

**Status Effects** are temporary effects that happen to a character or game object with a **Stats** component. These effects can either be positive to the affected \(_buff_\) or have negative effects \(_debuff_\).

{% hint style="info" %}
An example of a common **Status Effect** is **Poison**, which drains health from the player for as long as it is active.
{% endhint %}

Status Effects have some common properties, such as a localizable **name**, a **description**, an **icon** and a **color**. These properties can be used in the [Stats UI](../stats-ui.md).

![](../../../.gitbook/assets/status-effect-pref.jpg)

The most important part are the **Actions** they invoke. There are three of them:

### On Start

These **Actions** are executed as soon as the Status Effect starts and is intended to be used to initialize the effects of the status.

{% hint style="success" %}
For example, if a **Status Effect** increases the **`strength`** of the bearer, the **Action** executed **On Start** should be adding a **Stat Modifier** to the _Invoker_ object.
{% endhint %}

### While Active

These **Actions** have a very special behavior. Once they are finished they are called again until the **Status Effect** is worn off.

{% hint style="success" %}
For example, the Status Effect Poison, which drains health from the invoker should have two Actions:

* **Decrease** 5 points from the invoker's **health** **attribute**
* **Wait** 0.25 seconds
{% endhint %}

{% hint style="danger" %}
In order to maximize performance you should add a **Wait Action** at the beginning or the end of these **Actions**, so they are not invoked every frame.
{% endhint %}

### On End

These **Actions** are executed as soon as the **Status Effect** is worn off and should be used to restore the previous state of the affected object.

{% hint style="success" %}
For example, following the example of the **On Start**, where the character's strength is increased by 10 points, **On End** should remove the **Stat Modifier** that increases 10 points.
{% endhint %}

## Saving and Loading

It is worth noting that when a game is saved through the **Save/Load** system, the current **Status Effects** applied to the different objects are also saved.

When restoring a previously saved game, the **On Start** actions will be called for each **Status Effect** that was in effect when the game was saved. The remaining time of each Status Effect will also be the same as the one when the game was saved.

{% hint style="info" %}
**Example:** the Player has been infected with the **Poison Status Effect**, which has a duration of 30 seconds. The user saves the game 12 seconds after the player was afflicted and exists the game.

The next day, when the user loads the game, the player will be infected with the **Poison Status Effect** \(the On Start actions will be called\) and the remaining time will be 30 - 12 = 18 seconds.
{% endhint %}




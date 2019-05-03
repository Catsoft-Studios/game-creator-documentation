---
description: If A - Then B - Else C
---

# Conditions

{% hint style="danger" %}
**Conditions** were named as **Events** before they were renamed on version 0.7.1.
{% endhint %}

**Conditions** components a little bit more complex than **Actions**; they allow to check for conditions and branch from execution threads.

![\(Example of a Conditions object\)](../../.gitbook/assets/events.jpg)

Even if the concept seems complicated, it's actually fairly simple: Imagine you have a **Chest** that the player can loot. This **Chest** should only be looted once.

Upon clicking it, if it's the first time, the player gets some items. Otherwise a message can be prompted stating that the chest has already been looted.

## Anatomy of a Condition

**Conditions** work much like [Actions](actions.md), but instead of immediately being executed when called, they perform a set of _checks_ before deciding which action to call \(if any at all\).

![\(Conditions anatomy: Clauses contain pairs of Conditions - Actions\)](../../.gitbook/assets/event-anatomy.jpg)

A **Conditions** object follows the following process:

* Check the first **Clause**
  * If all **Conditions** are _true_
  * Then executes its **Actions**
* If not all **Conditions** where _true_, jump to the second **Clause**
  * If all **Conditions** are _true_
  * Then executes its **Actions**
* ...
* If any of the **Clause** **Conditions** was _true_, then execute a special **Actions**

Only one set of **Actions** will be called in a **Conditions**. If the first **Clause** of the **Conditions** are all true, only its **Actions** will be executed and the rest of the **Clause** won't even be checked.

{% hint style="info" %}
**Conditions** are hard to get at the beginning. For a more comprehensive explanation, watch the following tutorial.
{% endhint %}

{% embed url="https://www.youtube.com/watch?v=WbREQsACPjw" %}

## Available Conditions

Here's a list of all available **Conditions**. Remember that each module adds new ones to the list. You can also find more **Conditions** visiting the [Game Creator Hub](https://hub.gamecreator.io).

### Variables

| Condition Name | Description |
| :--- | :--- |
| **List Variables contains Object** | Returns True if a given Game Object can be found inside a List Variables |
| **List Variables Count** | Returns True if the amount of elements in a List Variables is greater or equal to a given value |
| **Variable Bool** | Compares a Variable with a boolean value |
| **Variable Color** | Compares a Variable with a Color value |
| **Variable Game Object** | Compares a Variable with a Game Object value |
| **Variable Number** | Compares a Variable with a Number value |
| **Variable Sprite** | Compares a Variable with a Sprite value |
| **Variable String** | Compares a Variable with a String value |
| **Variable Texture2D** | Compares a Variable with a Texture2D value |
| **Variable Vector2** | Compares a Variable with a Vector2 value |
| **Variable Vector3** | Compares a Variable with a Vector3 value |

### Characters

| Condition Name | Description |
| :--- | :--- |
| **Character Capsule** | Checks if the radius and height of a character is greater or equal than a value |
| **Character Property** | Compares the value of a Character Property with a given value. For example, the height of the Character, its radius, whether it is controllable or not, ... |

### General

| Condition Name | Description |
| :--- | :--- |
| **Pattern** | Returns True or False depending on the given pattern. For example, if the pattern is "**True**, **False**, **True**", the first 5 times the Condition is checked will return "**True**, **False**, **True**, **True**, **False**". Starts over again when reaching the end. |
| **Simple Condition** | Returns a constant value of True or False. Useful for debugging. |

### Input

| Condition Name | Description |
| :--- | :--- |
| **Keyboard** | Returns if a keyboard key is being pressed or not |
| **Mouse Button** | Returns if a mouse button is being pressed or not |

### Object

| Condition Name | Description |
| :--- | :--- |
| **Game Object Active** | Returns True if a given Game Object is active |
| **Exists Game Object** | Return True if a given Game Object exists |
| **Rigidbody** | Returns True if a given Game Object exists and contains a Rigidbody component |
| **Tag** | Returns True if a given Game Object has a given tag value |


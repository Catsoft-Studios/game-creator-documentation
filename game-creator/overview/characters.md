---
description: The living parts of your game
---

# Characters

The **Characters** component allows to define an object as a character. A **Character** can be moved around using the appropriate **Actions**. You can also tweak different properties such as if the character can _walk_, _run_, its _speed_ and more

![](../../.gitbook/assets/character.jpg)

Since version **0.2.5 **a character can also perform one of multiple **gestures**, such as waving its hand, picking an object, drinking a potion, ... And be in one of multiple states, such as crouched, injured and so on.

{% hint style="info" %}
Since version **0.2.6** a character can also **Jump**.
{% endhint %}

## Character Properties {#character-properties}

The **Character**'s properties is divided into two big sub-groups: The **Basic** properties, and the **Advanced** properties.

### Basic Properties {#basic-properties}

As its name implies, the **Basic** character properties are easily understandable and directly affect the **Character**'s behavior.

* **Is Controllable:** An on/off property that allows to set a character can be controlled with **Actions**.
* **Can Run:** A toggle property that restricts the speed of the character. If set to true, the maximum speed the character can move is `runSpeed`. Otherwise the `walkSpeed` will be used.
* **Walk Speed** and **Run Speed:** The lineal speed the character moves when walking/running.
* **Angular Speed:** The speed at which the character rotates towards its desired direction expressed in **degrees per second**. If this property is set to 180, a character will need one second to turn to its opposite direction.
* **Can Jump:** Allows to give the character the ability to jump. If set to false, even if the Character receive an order from an **Action** to jump, it won't do it.
* **Jump Force:** Default jump force used by the **Player** jump input and the **Jump Action**

### Advanced Properties {#advanced-properties}

The **Advanced** character properties are meant to be modified by more advanced users who need finer-grain control over the **Player** and other **NPC**s.

* **Slope Speed Up** and **Slope Speed Down:** In real life, a human doesn't move at the same speed when running on a flat surface as it does on a steep one. This parameter allows to define the amount \(percent\) of _speed_ that is subtracted from going up or down.
* **Face Camera Direction:** If checked, the character will always face where the camera's direction. Very useful when making a game from a First Person perspective.
* **Can Use Navigation Mesh:** If checked, the character will automatically use the _Unity's Navigation Mesh_ system when moving from one point to another and change back to using the _Character Controller_ if not moving. It is recommended to use this, as it allows to avoid obstacles when moving characters around the scene.

{% hint style="info" %}
**Can Use Navigation Mesh** is disabled by default because the user has to **Bake** the Navigation Mesh first. To know more about using the **Navigation Mesh** follow this [link](https://docs.unity3d.com/Manual/Navigation.html).
{% endhint %}

### Inverse Kinematics {#inverse-kinematics}

Since version 0.4.1 **Game Creator** allows the use of **Inverse Kinematics** \(aka **IK**\). This advanced technique allows to correctly place the feet of a character taking into account the steepness of the terrain, instead of relying on the animation of the character.

**Game Creator** goes one step further and has a custom feature called **Weight Compensation**, which allows the character to slightly elevate or crouch depending on the inclination of the floor, so not only the feet are properly aligned, but also the knees gracefully bend.

## Animating the Character {#animating-the-character}

In order to make the system more flexible, the **Character** and its animation system have been split in two different components.  



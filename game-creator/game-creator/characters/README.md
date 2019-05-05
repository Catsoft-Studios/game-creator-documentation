---
description: 'Hello, my name is...'
---

# Characters

The **Characters** component allows to define an object as a character. A **Character** can be moved around using the appropriate **Actions**. You can also tweak different properties such as if the character can _walk_, _run_, its _speed_ and more

![](../../../.gitbook/assets/character.jpg)

Since version **0.2.5** a character can also perform one of multiple **Gestures**, such as waving its hand, picking an object, drinking a potion, ... And be in one of multiple **States**, such as crouched, injured and so on.

{% hint style="info" %}
Since version **0.2.6** a character can also **Jump**.
{% endhint %}

## Character Properties <a id="character-properties"></a>

The **Character**'s properties is divided into two big sub-groups: The **Basic** properties, and the **Advanced** properties.

### Basic Properties <a id="basic-properties"></a>

As its name implies, the **Basic** character properties are easily understandable and directly affect how the **Character** moves.

![\(Character Basic Properties window\)](../../../.gitbook/assets/character-basic-properties.jpg)

* **Is Controllable:** An on/off property that allows to set a character can be controlled with **Actions**.
* **Can Run:** A toggle property that restricts the speed of the character. If set to true, the maximum speed the character can move is `runSpeed`. Otherwise it will use the walk speed, which is half of the run speed.
* **Run Speed:** The lineal speed the character moves when running.
* **Angular Speed:** The speed at which the character rotates towards its desired direction expressed in **degrees per second**. If this property is set to 180, a character will need one second to turn to its opposite direction.
* **Gravity:** The downwards force amount that the character experiences
* **Max Fall Speed:** Maximum fall speed. Setting a low value allows the character to glide.
* **Can Jump:** Allows to give the character the ability to jump. If set as false, even if the Character receive an order from an **Action** to jump, it won't do it.
* **Jump Force:** Default jump force used by the **Player** jump input and the **Jump Action**
* **Jump Times:** Amount of times the Character can jump before touching the ground. Also known as double jumping, triple-jumping, etc...
* **Time Between Jumps:** The minimum offset time between jumps.

### Advanced Properties <a id="advanced-properties"></a>

The **Advanced** character properties are meant to be modified by more advanced users who need finer-grain control over the **Player** and other **NPC**s.

![\(Character Advanced Properties window\)](../../../.gitbook/assets/character-advanced-properties.jpg)

* **Face Camera Direction:** Controls where the Characters has its body oriented based on the direction it's moving. Can either be:
  * **Move Direction:** The Character rotates towards where it is going
  * **Camera Direction:** The Character looks at the same direction as the camera. The Character will strafe when moving sideways. This movement is useful for aiming weapons
  * **Target:** The Character always faces a target, strafing when orbiting around it
  * **Ground Plane Cursor:** The Character looks at the direction in which the cursor is. Useful for top down shooters.
* **Can Use Navigation Mesh:** If checked, the character will automatically use the _Unity's Navigation Mesh_ system when moving from one point to another and change back to using the _Character Controller_ if not moving or there's no _Navigation Mesh_. It is recommended to use this, as it allows to avoid obstacles when moving characters around the scene.
* **Save:** Tells Game Creator to keep track of the character's position and rotation. When loading a saved game, it will restore the Character's position and rotation to its saved location.

{% hint style="info" %}
**Can Use Navigation Mesh** is disabled by default because the user has to **Bake** the Navigation Mesh first. To know more about using the **Navigation Mesh** follow this [link](https://docs.unity3d.com/Manual/Navigation.html).
{% endhint %}

## Animating the Character <a id="animating-the-character"></a>

In order to make the system more flexible, the **Character** and its animation system have been split in two different components.

![\(You can customize the Animator parameters if you already have a Character system\)](../../../.gitbook/assets/character-animation.jpg)

The **Character Animator** has four different sections: 

* Animator Parameters
* Character Model
* Inverse Kinematics
* Ragdoll

### Animator Parameters <a id="animator-parameters"></a>

{% hint style="success" %}
This is an advanced feature and should not be modified unless you know exactly what you're doing. You can safely skip this step and ignore the **Animator Parameters** section.

For information about how to animate a character, see the [Gestures](gestures.md) and [States](states.md) sections.
{% endhint %}

These string values behave as a proxy between the **Character** component and the **Animator**, gathering locomotion information from the logic controller and plugging it into the **Animator**. The string values defined inside the **Animator Parameters** allow to have a custom **Animator Controller**.

{% hint style="warning" %}
We don't recommend tweaking these parameters unless you are certain of what you want to do. In case you want to use your own Animation solution, you can access the current **Character** state by calling a public method named **`GetCharacterState()`**. It returns a **`Character.State`** class with information about if the character is grounded or not, its direction, etc.
{% endhint %}

### Character Model <a id="character-model"></a>

You'll probably want to make a game with your custom character models. Luckily, changing between characters in **Game Creator** is as easy as clicking the **Change Model** button and dragging in the 3D model you want to use from your _Project Panel_. **Game Creator** will take it from here and automagically update the character with the new one.

![\(Automagically retarget any Humanoid bone structure with our Locomotion system\)](../../../.gitbook/assets/character-change-model.gif)

{% hint style="info" %}
You can also change characters in **Play-Mode** in case you want to see how they look like. Switching back to **Edit-Mode** will undo any changes made.
{% endhint %}

### Inverse Kinematics

Since version 0.4.1 **Game Creator** allows the use of **Inverse Kinematics** \(aka **IK**\). This advanced technique allows to correctly place the feet of a character taking into account the steepness of the terrain, instead of relying on the animation of the character.

**Game Creator** goes one step further and has a custom feature called **Weight Compensation**, which allows the character to slightly elevate or crouch depending on the inclination of the floor, so not only the feet are properly aligned, but also the knees gracefully bend.

{% hint style="warning" %}
Enabling **IK** comes at a \(minimal\) performance cost of several **Raycasts** per frame. 
{% endhint %}

#### Foot IK

Foot IK allows any Character or Player to correctly align and place their feed even on steep floors.

![\(With just one click your Characters will realistically align their feet and body to the floor\)](../../../.gitbook/assets/character-ik.gif)

#### Hand IK

Allows the **Character** to correctly place the hands on certain targets. For example, if the player is driving a car, it can keep the hands on the wheel in spite of the rotation or if the character is holding a weapon, it can correctly place its hands.

![\(Hand IK set to reach out for the Red Cube\)](../../../.gitbook/assets/character-hand-ik.gif)

#### Head IK

Allows the Character to slightly rotate its head towards a target. This adds a new layer of realism when moving the character around the world or interacting with other Characters.

![\(Head IK smoothly following a Red Cube\)](../../../.gitbook/assets/head-ik-example.gif)

{% hint style="info" %}
**Hotspots** take advantage of the **Head IK** and allow to make the character automatically look at the point of interest when the **Character** is near
{% endhint %}

## Custom Animations

You can play custom animations created by you or downloaded from third-party services, such as [Mixamo](https://mixamo.com). To do so, you need to make sure that the imported animation is of type **Humanoid**. 

By default, Unity imports its animations as Generic. To change the animation type, select the imported clip and click on the **Rig** tab. There you can select Humanoid under **Animation Type**. 

![\(Animation Type set as Humanoid\)](../../../.gitbook/assets/character-humanoid.png)

For more information on how to play custom animations, Game Creator provides two components built on top of the Unity's Animation system: [Gestures](gestures.md) and [States](states.md). Check them out to know how to play simple animations or even build complex locomotion movements with just a couple of clicks.


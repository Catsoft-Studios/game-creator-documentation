---
description: Become the movie director
---

# Camera Motors

**Camera Motors** tell the **Camera Controller** where and how to look at the world. There are a bunch of different types of motors.

## Fixed Camera Motor {#fixed-camera-motor}

This is the simplest type of **Camera Motor**. It stays at a fixed position, just like a _surveillance security camera_ and it can rotate to look at different types of targets.

![\(Fixed cameras rotate towards their target\)](../../../.gitbook/assets/camera-fixed.jpg)

* **Default**: Doesn't rotate
* **Player**: Looks at the player
* **Target**: Looks at a specific target
* **Position**: Looks at a specific world-space position

## Follow Camera Motor {#follow-camera-motor}

The **Follow Camera Motor** is similar to the **Fixed Motor** as it allows to look at a specific target/position/player but it also allows to follow it.

![\(Follow Cameras keep a constant distance from their anchor target\)](../../../.gitbook/assets/camera-follow.jpg)

{% hint style="info" %}
This type of camera is usually used for **RTS** or **Top-Down** games.
{% endhint %}

{% hint style="success" %}
There is a little dampening between the position of the target and the actual movement of the camera to prevent it from jittering.
{% endhint %}




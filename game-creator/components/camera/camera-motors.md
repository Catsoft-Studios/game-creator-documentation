# Camera Motors

**Camera Motors** tell the **Camera Controller** where and how to look at the world. There are a bunch of different types of motors.

## Fixed Camera Motor <a id="fixed-camera-motor"></a>

This is the simplest type of **Camera Motor**. It stays at a fixed position, just like a _surveillance security camera_ and it can rotate to look at different types of targets.

![\(Fixed cameras rotate towards their target\)](../../../.gitbook/assets/camera-fixed.jpg)

* **Default**: Doesn't rotate
* **Player**: Looks at the player
* **Target**: Looks at a specific target
* **Position**: Looks at a specific world-space position

## Follow Camera Motor <a id="follow-camera-motor"></a>

The **Follow Camera Motor** is similar to the **Fixed Motor** as it allows to look at a specific target/position/player but it also allows to follow it.

![\(Follow Cameras keep a constant distance from their anchor target\)](../../../.gitbook/assets/camera-follow.jpg)

{% hint style="info" %}
This type of camera is usually used for **RTS** or **Top-Down** games.
{% endhint %}

{% hint style="success" %}
Add a little dampening to the **Camera Controller** to avoid jittering.
{% endhint %}

## Target Camera Motor <a id="target-camera-motor"></a>

The **Target Camera** behaves much similar like the **Follow Camera** but also accepts a **Look At** target. It's mostly used for _Shoulder_ cameras where the camera is anchored to a position \(Player's shoulder\) but the focus of the camera is targeting another scene object.

![\(Camera orbits around the anchor while keeping both the anchor and target inside the screen\)](../../../.gitbook/assets/camera-target.jpg)

{% hint style="success" %}
This camera can also be used to highlight a place of interest
{% endhint %}

## Railway Camera Motor <a id="railway-camera-motor"></a>

The **Railway Camera Motor** is a little bit more sophisticated type of motor. It allows the camera to follow the target along a path \(or rail\) but never exceed it.

![\(Railway cameras also have scene gizmos\)](../../../.gitbook/assets/camera-railway.jpg)

Railway Cameras are a bit difficult to understand at first but are a powerful tool to create cinematic experiences.

![\(See how the camera follows the blue ball when it&apos;s inside its constrained bounds\)](../../../.gitbook/assets/camera-railway-demo.gif)

The player \(_blue ball_\) moves from right to left. When the player is within the _plane_ of the blue line, the camera linearly interpolates the player's position with its min-max path.

{% hint style="info" %}
In other words, the camera follows the **Player** as long as the **Player** is within the blue line. Otherwise it stays at the edge of the path.
{% endhint %}

This type of cameras are very useful for corridors or narrow rooms.

{% hint style="info" %}
You can modify the camera path and the player min-max path by clicking and dragging the white balls in the scene view.
{% endhint %}

## Tween Camera Motor <a id="tween-camera-motor"></a>

The **Tween Camera Motor** allows to move the camera from a position _A_ to position _B_ within a time window. It is mostly used for cutscenes or small animations.

![\(Move the camera from A to B within a time window\)](../../../.gitbook/assets/camera-tween.jpg)

Tween Camera Motors are easily set up using the scene view gizmos. The motor's position corresponds to the initial position while the white dot is the end position

![](../../../.gitbook/assets/camera-twee-scene.jpg)

## First Person Camera Motor <a id="first-person-camera-motor"></a>

The **First Person Motor** allows to create FPS action games like _Call of Duty_ or horror games like The Elder Scrolls.

![\(Max pitch avoids overshooting rotations\)](../../../.gitbook/assets/camera-fps.jpg)

This camera motor allows to define the mouse sensitivity, the amount of dampening/spring the camera moves relative to the mouse and the maximum pitch rotation \(in case you want to limit the visual spectrum of the player\).

## Adventure Camera Motor <a id="adventure-camera-motor"></a>

The **Adventure Camera** is an advanced camera system that behaves like the cameras from _Tomb Raider_ or _Uncharted_ series.

![\(Adventure Camera Motor has a quite a few configuration parameters\)](../../../.gitbook/assets/camera-adventure.jpg)

The camera orbits around a target using the mouse movement \(on Desktop\) or using the touch-screen if the target device is mobile.

{% hint style="success" %}
You can also toggle whether you want to avoid **wall collision**.
{% endhint %}


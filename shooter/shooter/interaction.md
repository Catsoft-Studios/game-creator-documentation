---
description: 'How to Pew, Pew, Pew!'
---

# Interaction

The two previous chapters we overviewed how to create a **Weapon** and an **Ammo** object, as well as see what each option does. In this chapter we'll see how to put everything together and make **Characters** make use of the **Weapon** and **Ammo** objects in order to pull, aim and shoot at stuff.

## Character Shooter

The **Character Shooter** component is a special component that must be added to each **Character** that is going to hold a weapon. 

{% hint style="info" %}
If this component is not detected, **Game Creator** will automatically add it for your, but it's better if you add it yourself in the editor, or you'll miss some features, such as saving the amount of ammunition.
{% endhint %}

{% hint style="danger" %}
The **Player** should use another component called **Player Shooter** instead. This will allow it to use different aiming modes, unavailable to NPCs.
{% endhint %}

## Drawing & Holstering Weapons

Drawing and holstering weapons is done using the **Weapon Draw** and **Weapon Holster Actions**. These automatically equip the character with the specified weapon. 

The **Ammo** field is optional and, if none is specified, it will use the default Ammo object defined by the Weapon.

## Aiming

Aiming is the process of choosing a target at which to shoot at. There are multiple aiming types, each addressing requirements set by different types of games. Here is the full list of options available when using the **Aim Weapon Action**.

* **Stop Aiming:** Used to stop aiming with the weapon. Typically used when releasing the aiming button.
* **Aim Camera Direction:** Aims where the camera looks at. Perfect for Third-Person and First-Person shooter games.
* **Aim at Target:** The target is specified by a Transform object and keeps track of its position.
* **Aim at Position:** The target is specified by a given position.
* **Aim Muzzle Forward:** Simply aims forward, where the character with the weapon is shooting at.
* **Aim Ground Plane:** Aims at a direction specified by the projection of the mouse over the plane where the character is. This option is perfect for top-down shooter games.
* **Aim Side-Scroll:** Aims at  a direction specified by the project of the mouse over the vertical plane of one side of the character. The plane \(XY or ZY\) can be also specified.

{% hint style="info" %}
It is important to distinguish the difference between **Aim at Target** and **Aim at Position**. The first one will make the character keep track of the target while it is aiming, while the other one will remember the position of the target, but, if this one moves, it will still aim at where it was at the beginning.

As a rule of thumb, **Aim at Target** should only b used with the _player_, as you normally lock onto enemies. On the other hand, **Aim at Position** is usually used by enemies to simulate a flaw in their accuracy.
{% endhint %}

## Shooting

{% hint style="warning" %}
**UNDER CONSTRUCTION**
{% endhint %}

## Receiving Damage

{% hint style="warning" %}
**UNDER CONSTRUCTION**
{% endhint %}


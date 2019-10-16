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

Shooting a weapon is very simple. All that is needed is to use the **Shoot Weapon Action**. This will instruct the weapon to shoot. Depending on both the currently equipped **Weapon** and **Ammo** assets, the shot will be different.

However, there's a second type of shot that requires a different set of Actions: The charged shots.

Charged shots need a wind-up time before being released. An example of a charged shot are grenades, bows, Megaman's ArmGun, etc...

To start charging a shot you need to use the **Weapon Start Charged Shot**. To execute a charged shot you'll need to use the **Weapon Execute Charged Shot**.

{% hint style="warning" %}
Notice that nothing will happen if the **Execute Charged Shot** is issued before the **Start Charged Shot**.

Charged shots also have a minimum charge time, which defines the minimum time required to be able to shoot a charged shot. If the time between **Start Charged Shot** and **Execute Charged Shot** is less than the **`Min Charge Time`** field in the **Ammo** asset, the shot will not be made.
{% endhint %}

## Receiving Damage

Receiving damage is an essential step in any game where any kind of shooting is involved. There are two ways to deal with damage output: The first one is using the built-in **Action Lists** provided by each **Ammo** asset. When shooting with any raycast or trajectory-cast projectiles, the Invoker will always reference the targeted object.

However, this does not give enough control. To solve this, there's the **On Receive Shot** **Trigger**, which is executed any time it received a shot. These shots can be filtered by weapon type and shot type \(Any, Normal or Charged\).

{% hint style="info" %}
Raycast shooting modes will always automatically look for any **On Receive Shot** **Trigger** and call it. However, projectiles do not. In order for a _Grenade_ or an _Arrow_ \(or any prefab projectile\) to trigger the **On Receive Shot**, these need to use the **Notify Shot Action**.

For example, the _Arrow_ projectile has a **On Collision Enter Trigger** which uses the **Notify Shot Action** to whatever object it collides with. The G_renade_, on the other hand, collects all the objects affected by the blast and uses the **Notify Shot Action** in each one of them.
{% endhint %}




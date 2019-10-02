---
description: shooter.Fire(bullet);
---

# Shooter API

Same way you use **Triggers**, **Conditions** and **Actions** to interact with the **Shooter** module, you can write your own scripts to do the same. Here's an overview of the **Shooter API**.

## Character Shooter

The **`Character Shooter`** component contains a bunch of public methods that allow you to interact with how this **Character** will behave. It is important to notice that the **Player** uses another component called **`Player Shooter`**, but it inherits from **`Character Shooter`**, so everything available in one is available too on the other one.

### Events

There are a few events you can subscribe to in order to react when the Character Shooter performs certain tasks.

* **`eventEquipWeapon<Weapon>`** Event raised whenever the Character equips a weapon.
* **`eventUnequipWeapon<Weapon>`** Event raised whenever it unequips a weapon.
* **`eventChangeAmmo<Ammo>`** Event raised whenever it changes its type of ammo.
* **`eventReload<Weapon, Ammo>`** Event raised whenever the Character reloads.
* **`eventShoot<Weapon, Ammo>`** Event raised whenever the Character shoots.
* **`eventChargedShotStart<Weapon, Ammo>`** Event raised whenever it starts charging.
* **`eventChargedShotStop<Weapon, Ammo>`** Event raised whenever it ends a charged shot.

### Queries

You can also query different states without any performance overheads. All queries start with the prefix **`is-`** and return a bool.

* **`isAiming`** Returns true if the Character is aiming
* **`isChargingShot`** Returns true if the Character is charging a shot
* **`isReloading`** Returns true if the Character is currently reloading the gun
* **`isDrawing`** Returns true if the Character is pulling the gun
* **`isHolstering`** Returns true if the Character is holstering the gun

### Methods

There are many methods from which 


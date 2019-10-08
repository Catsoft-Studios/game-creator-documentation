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
* **`eventAim<bool>`** Event raised whenever the Character starts or stops aiming

### Queries

You can also query different states without any performance overheads. All queries start with the prefix **`is-`** and return a bool.

* **`isAiming`** Returns true if the Character is aiming
* **`isChargingShot`** Returns true if the Character is charging a shot
* **`isReloading`** Returns true if the Character is currently reloading the gun
* **`isDrawing`** Returns true if the Character is pulling the gun
* **`isHolstering`** Returns true if the Character is holstering the gun

### Methods

There are many methods that allow you to interact with the Shooter module. 

{% hint style="danger" %}
**IMPORTANT!** Some methods return an **`IEnumerator`**. This methods are coroutines and can't be called like you would normally do, but instead:

`StartCoroutine(this.Method_I_Want_To_Call());`

Notice how the method is called inside the **`StartCoroutine`**, not just passed as an argument. For more information about **Coroutines**, follow this [link](https://docs.unity3d.com/Manual/Coroutines.html).
{% endhint %}

**`IEnumerator ChangeWeapon(Weapon weapon, Ammo ammo = null)`**

Changes the currently equipped weapon and ammunition. If no ammunition is provided, the one set by default in the weapon will be used.

**`void ChangeAmmo(Ammo ammo)`**

Changes the currently equipped ammunition

**`IEnumerator Reload()`**

Reloads the currently equipped weapon if possible

**`void StartAiming(AimingBase aiming)`**

Starts aiming with the weapon. It is required for the Character to be holding a weapon before. The `AimingBase` class is an abstract class that requires an instance from one of the following specific classes:

* **`AimAtTarget`** Aims at a specific target and will keep pointing at it until told otherwise. Useful for locking in targets.
* **`AimingCameraDirection`** Aims where the camera looks at. Useful for games that use the first person motor or the adventure camera motor.
* **`AimingGroundPlane`** Aims where the mouse points at, along the surface of a horizontal plane surrounding the shooter. Specifically designed for top-down shooters.
* **`AimingMuzzleForward`** Aims where the muzzle points.
* **`AimingSideScrollPlane`** Aims where the mouse is along a vertical plane. This plane can be set along the X axis or the Z axis. Specifically designed for side scroll games.

**`void StopAiming()`**

Stops aiming with the weapon.

**`void Shoot()`**

Shoots wherever the character is aiming at. Mind that where the Character aims at is specified using the `StartAiming` method.

**`void StartChargedShot()`**

Starts charging a shot. This method must always be proceeded by the `ExecuteChargedShot()`.

**`void ExecuteChargedShot()`**

Executes a charged shot. This method must be preceded by a `StartChargedShot()`. Otherwise it will be ignored.

**`float GetCharge()`**

Gets the amount of charge being accumulated. The result is a value between 0 and 1, which indicates the percentage of the charge. 

This method should always be called between `StartChargedShot()` and `ExecuteChargedShot()`. Otherwise it will always return 0.

**`int GetAmmoInClip(string ammoID)`**

Returns the amount of ammunition in the weapon's clip. The **`ammoID`** is the identifier of the Ammo object.

**`int GetAmmoInStorage(string ammoID)`**

Returns the amount of spare ammunition the character has. This is the total amount of ammunition available minus the amount in the clip.

**`void SetAmmoToClip(string ammoID, int amount)`**

Sets the amount of ammunition in the clip without triggering a reload.

**`void AddAmmoToClip(string ammoID, int amount)`**

Adds the amount of ammunition specified in the clip without triggering a reload.

**`void SetAmmoToStorage(string ammoID, int amount)`**

Sets the amount of spare ammunition.

**`void AddAmmoToStorage(string ammoID, int amount)`**

Adds a certain amount of ammunition to the spare ammo. This method is the one that should be called whenever the Character collects ammo from enemies killed or around the environment.

{% hint style="warning" %}
There are a few more undocumented methods available, but shouldn't be of interested. However, if you are curious about them, you can open the **`CharacterShooter`** script and examine them. The names are quite self-describing.
{% endhint %}


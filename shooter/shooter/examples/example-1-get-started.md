# Example 1 - Get Started

This first example shows how to set up a basic shooter controls, which are later expanded with new features in the rest of the examples. In this section, we'll go over the key elements.

![](../../../.gitbook/assets/example1-header.jpg)

## Player

The Player's configuration is really simple. It's just been added the **`PlayerShooter`** component, which handles ammunition, displaying the correct crosshair \(if any\) as well as keep track of the weapon being used.

## Common Triggers

This prefab is used throughout all the scenes and it's a handy way of reusing the same shooting mechanics in multiple scenes.

{% hint style="info" %}
The **Weapon** and **Ammo** assets configure how the weapon behaves, but do not bind any key strokes to the shooting, charging and drawing/holstering. This is done using Actions, Conditions & Triggers.
{% endhint %}

### Drawing & Holstering

Drawing and holstering a weapon is done pressing the **`E`** keyboard button. This is specified using a Trigger that detects _On Key Down_ with the _E_ option.

This **Trigger** executes a **Condition** object that checks whether the **Player** has a weapon at hand or not. If it does not, it uses the **Draw Weapon** action referencing the _Revolver_ weapon asset. Otherwise, it uses the **Holster Weapon** action.

### Aiming

Before shooting with a weapon the character with the weapon must first aim with it. There are multiple aiming systems available, each used in different situations \(for example, it's not the same aiming with a weapon if your game has a top-down perspective, or it is a side-scroll game or a first-person shooter\).

Similarly to the drawing/holstering **Triggers**, we're binding the **`Left Shift`** key to the aiming. Using a **On Key Down Trigger** \(with the **`Left Shift`** option\) will use the **Aim Weapon Action**, whereas another **On Key Up Trigger** \(also with the **`Left Shift`** option\) will use the **Aim Weapon Action**, but the option to _Stop Aiming_.

### Charging & Shooting

Shooting a weapon is done via the **Shoot Action**. However, there are two types of shots in the **Shooter** module:

* _Instantaneous shot_, which is how most weapons work.
* _Charged shots_, like bows or grenades, which require wind up time.

If you try to charge a weapon that doesn't allow a charged shot, the **Action** will be ignored. Respectively, if you try to shoot normally a weapon that requires some charge time, it will also be ignored. This limitation is very useful, since you can bind keys to different charge and shooting Actions and only those that suit will be executed.

In this case, we're binding the _Left Mouse_ button to the normal shot, using a **On Mouse Down Trigger** with the _Left Button_ option. This **Trigger** executes the **Shoot Action**.

{% hint style="info" %}
Notice that the weapon will fire every time the user clicks with its left mouse button. If you want to shoot continuously while holding the left button \(like an assault rifle would do\), you can add a **Restart** Actions right below the **Shoot** Action. This will loop the Action indefinitely. 

To stop the weapon from firing, you'll also need to create a **On Mouse Up** Trigger with the _Left Button_ option, which will use the **Cancel** Action on the previous action. This will force the action responsible for the shooting to exit its execution cycle.
{% endhint %}

To shoot charged attacks, there are to phases: The charging and the release of the charge. We've bound these mechanics to the right mouse button, so when the user holds down the button, the player will start charging the attack. When releasing the button, the charged attack will be executed.

To do this, we simply use two **Triggers**: **On Mouse Down** for charging and **On Mouse Up** for releasing the shot.

The **On Mouse Down Trigger** will execute the **Start Charged Shot Action**. The **On Mouse Up Trigger** will execute the **Execute Charged Shot**.

{% hint style="success" %}
Remember this is just the configuration we decided to use. You can use whatever input schema that suits your game.
{% endhint %}




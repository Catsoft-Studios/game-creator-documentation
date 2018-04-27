# Player

The **Character Player** inherits all the functionalities from the **Character** component. This section assumes you are familiar with the **Character** component.

The player is just a **Character** with a custom **section** called **Input** that allows to define which user's keys/button/joystick inputs do what. 

{% hint style="info" %}
If the **IsControllable** property is set to false, the player won't respond to the user's input.
{% endhint %}

The Player has different input methods:

* **Directional:** Move the player using the WASD keys or a joystick.
* **Point & Click:** Click on the floor and the Player will move there. It can use the Navigation Mesh.
* **Pointer Follow:** Moves towards the direction of the pointer.

{% hint style="info" %}
In mobile devices the **Directional** input will pop a **Virtual Joystick**.
{% endhint %}

You can also define which key will make the **Player** jump, though bear in mind that if the Player has the **Can Jump** checkbox set to false, it won't jump.


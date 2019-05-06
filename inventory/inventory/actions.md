# Actions

The **Inventory** module includes a set of **Actions** that complement **Game Creator**'s and allow to _do_ things with **Items**, **Recipes** and the player's **Currency**.

{% hint style="info" %}
The **Player** **Inventory** is where all the items being carried are stored. this inventory is automatically saved when calling the **Save** Action so you don't need to worry about losing data between play sessions.
{% endhint %}

### Currency

Allows to _Add_ or _Subtract_ currency from the Player's Inventory.

### Instantiate Item

Instantiates \(adds to the scene\) a copy of the _Prefab_ associated to the **Item**.

{% hint style="info" %}
For example, you can instantiate a 3D model of a potion that adds 1 Potion item to the players to simulate dropping and picking it again.
{% endhint %}

### Item

Allows to manipulate an **Item**. You can either _Add_ the item to the Player's Inventory, _Substract_ a certain amount of _Consume_ the ones it has.

### Inventory UI

Opens or closes the Player's Inventory UI.

### Use Recipe

Tries to find a **Recipe** with the two select **Items**. If it successfully finds one, it combines those objects executing the previously defined **Actions** associated to the **Recipe**.

### Shop

Allows to _Buy_ or _Sell_ an **Item** \(and a defined amount of these\). The difference between _Buying_ and _Adding_ is that an **Item** has a price. If the player doesn't have enough **Currency** to purchase the **Item/s**, then it won't do anything. The same applies to _Selling_. If the player is not carrying enough **Items** in his inventory, the transaction won't be fulfilled.

### Equip Item

Equips an item from the Inventory \(if possible\). For more information about equipping items click [here](equip-items.md).

### Unequip Item

Unequips an item or everything from an Equippable Slot. For more information about equipping items see the [Equip Items](equip-items.md) section.

### Items List UI

An advanced **Action** used for the Inventory UI. Allows to modify what items are displayed in an **Items List** component. For more information about the **Items List** component see [Custom Inventory UI](custom-inventory-ui.md) section.

### Use Loot Table

Executes a **Loot Table**, giving the **Player** \(or adding to a **Container**\) a random item picked from a **Loot Table**. For more information on **Loot Tables** see the [Loot Tables](loot-tables.md) section.

### Merchant UI

Shows or hides the **Merchant UI**. For more information about **Merchants**, see the [Merchants](merchants.md) section.

### Container

**Container** **Actions** allow to interact with a **Container**. For more information about **Containers** see the [Containers](containers.md) section.

#### Add Item

Adds an item to a Container

#### Dump Inventory

Dumps the whole Player Inventory into a Container. This is useful when your game has multiple playable characters, each one with its own Inventory. 

{% hint style="success" %}
For example, if your game has 3 playable characters, when switching from **Player A** to **Player B**, you can dump the **Inventory** contents to a **Container A** and retrieve everything from **Container B**.
{% endhint %}

#### Retrieve Everything

Dumps everything from a **Container** to the **Inventory**. Useful when your game has multiple playable characters or you want to add a "Retrieve Everything" button when opening a Chest.

#### **Container UI**

Opens or closes the **Container UI** of a **Container**. The **Container UI Action** accepts multiple UI skins so your containers can look different from one and another.


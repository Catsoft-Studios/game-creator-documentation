# Custom Inventory UI

Every game is unique in its own way and even though two games of the same genre might share some similarities, the truth is that there aren't two games with the same **inventory** visuals.

**Inventory** module comes with a couple of inventory representations. The first one is called **RPG Inventory UI** and looks very similar to the ones you find in most Western RPG games, such as _The Witcher 3: Wild Hunt_ or _The Elder Scrolls: Oblivion_ \(_Skyrim_ had a vertical layout\). These types of inventories occupy most of the screen space and are perfect to _do things_ within the inventory, such as combining items, consuming them, and so.

The other inventory representation reminds more of old-school adventure games such as _Day of the Tentacle_, _TellTale Game's Tales from the Borderlands_ or any _Room Escape_ game. This types of inventories leave as much screen space as possible and allow to drag and drop items onto the screen. These inventories are more fit if you intend to add more interaction outside the inventory than inside.

## UI Overview {#ui-overview}

The only difference between these two inventories is their layout. Yes, seriously. We first created the **RPG Inventory**, we duplicated it and then, in less than 2 minutes, we had finished the **Adventure Inventory**.

An Inventory representation is composed of two prefabs:

* **Inventory UI Prefab**: Which is the actual representation of the inventory.
* **Item UI Prefab**: Which is the representation of an item that will be instantiated inside the **Inventory UI Prefab**.

We recommend that, if you want to create your own custom inventory, you duplicate any of the default prefabs we've set up.

{% hint style="info" %}
You can find these prefabs at: Assets/Plugins/GameCreator/Inventory/Prefabs/
{% endhint %}

Once you duplicate any of the **Inventory UI** and **Item UI** prefabs, drag and drop them in the Settings menu of the Inventory's [Preference Window](inventory-window/).

## Customizing the Inventory UI

Customizing how the Inventory looks like is very easy. Just drop the duplicated prefab in the scene and change the sprites and layouts in order to look like how you want it.

The _items container_ \(where the items will be placed\) should have an [AutoLayout component](https://docs.unity3d.com/Manual/UIAutoLayout.html). An auto-layout component can be either a [HorizontalLayoutGroup](https://docs.unity3d.com/Manual/script-HorizontalLayoutGroup.html), a [VerticalLayoutGroup](https://docs.unity3d.com/Manual/script-VerticalLayoutGroup.html) or a [GridLayoutGroup](https://docs.unity3d.com/Manual/script-GridLayoutGroup.html).

> Note that the **RPG Inventory UI** has a `GridLayoutGroup` while the **Adventure Inventory UI** has a `HorizontalLayoutGroup` for their items container.


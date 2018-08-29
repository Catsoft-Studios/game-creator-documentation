---
description: Hit Points for everyone
---

# Attributes

**Attributes** are very similar to **Stats** but their value ranges from 0 up to a maximum defined by a **Stat**. For example, the current health of a character is an attribute.

![\(The vitality Stat marks the max amount of health, while the Attribute value defines the current health\)](../../../.gitbook/assets/attribute-pref.jpg)

## Attributes in Runtime

**Attributes** are represented as a gauge or progress bar in the **Stats component** inspector. In the **Editor**, an attribute is displayed as the initial percentage filled. In **Play Mode**, however, the values change to display the current values.

![\(Editor mode of the Stats component\)](../../../.gitbook/assets/stats-component.jpg)

## Actions

There are some **Actions** that let you interact and query attribute values and states.

* **Change Attribute:** Allows you to change the base value of an attribute. The value can come from a variable of be a constant value
* **Sync Attribute to Variable:** Assigns the current value of an Attribute to a specific global or local variable.
* **Debug Attribute:** Prints the value of an attribute in the console

## Conditions

Same as Actions, Conditions with attributes allow to use the Stats features outside of the module, such as in the Inventory, Dialogue modules or even your own custom systems

* **Attribute Value:** Returns the final value of an attribute and compares it to another constant or variable number.


---
description: Go from * Ah! * to * GROAARGH!!! *
---

# Stat Modifiers

**Stat Modifiers** add a new layer to the value of the **Stats**. For example, the **`strength`** stat of a character might be **25**. If the character then equips with a _Steel Sword_, this could add a **Stat Modifier** of **+5** to the **`strength`**, which would make the character have a **`strength`** of **30**.

A Stat Modifier can either be a constant value or multiplicative.

* **Constant** values add \(or subtract if negative\) to the current stat. For example, adding -3 to vitality will decrease the vitality in 3 points.
* **Multiplicative** values increase the values by a percentage. For example, using a multiplicative value of -20% will increase a stat of 200 to 240.

{% hint style="info" %}
You may notice that calculating the final value of a **Stat** depends on the order of operands: It's not the same adding +5 to **`strength`** and then multiplying the result by a 10% than multiplying the base value by 10% and then adding 5 points.

You don't need to worry about the order in which **Stat Modifiers** are applied. This is automatically handled for you.
{% endhint %}

## Saving & Loading

{% hint style="danger" %}
**Stat Modifiers** are not saved nor loaded
{% endhint %}

This is a decision by design and has a logical explanation. When a **Stat Modifier** is added it's usually because of an external event to the character. For example, equipping a _sword_ that increases the **`strength`** by 5 or getting a **Status Effect** that decreases the **`agility`** by 20%.

When a game is loaded, all previously saved **Status Effects** are also initialized, executing their **On Start Actions**. Same happens with equipment.

If **Stat Modifiers** were to be also saved, they would be duplicated every time a game was loaded, due to the loading and initialization of their originators and the creation of the saved ones.


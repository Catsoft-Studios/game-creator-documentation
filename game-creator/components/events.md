# Events

Events components a little bit more complex than Actions; they allow to check for conditions and branch from execution threads.

![\(Example of an Event that checks if a chest is open or not\)](../../.gitbook/assets/events.jpg)

Even if the concept seems complicated, it's actually fairly simple: Imagine you have a **Chest** that the player can loot. This **Chest** should only be looted once.

Upon clicking it, if it's the first time, the player gets some items. Otherwise a message can be prompted stating that the chest has already been looted.

## Anatomy of an Event

**Events** work much like [Actions](actions.md), but instead of immediately being executed when called, they perform a set of _checks_ before deciding which action to call \(if any at all\).

![\(Event anatomy: Interactions contain pairs of Conditions - Actions\)](../../.gitbook/assets/event-anatomy.jpg)

An **Event** follows the following process:

* Check the first **Interaction**
  * If all **Conditions** are _true_
  * Then executes its **Actions**
* If not all **Conditions** where _true_, jump to the second **Interaction**
  * If all **Conditions** are _true_
  * Then executes its **Actions**
* ...
* If any of the **Interaction**'s **Conditions** was _true_, then execute a special **Actions**

Only one set of **Actions** will be called in an **Event**. If the first **Interaction**'s **Conditions** are all true, only its **Actions** will be executed and the rest of the **Interactions** won't even be checked.

{% hint style="info" %}
**Events** are hard to get at the beginning. For a more comprehensive explanation, watch the following tutorial.
{% endhint %}

{% embed url="https://www.youtube.com/watch?v=WbREQsACPjw" %}


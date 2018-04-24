---
description: Wrap Actions around conditions
---

# Events

Events components a little bit more complex than Actions; they allow to check for conditions and branch from execution threads.

![\(Example of an Event that checks if a chest is open or not\)](../../.gitbook/assets/events.jpg)

Even if the concept seems complicated, it's actually fairly simple: Imagine you have a **Chest** that the player can loot. This **Chest** should only be looted once.

Upon clicking it, if it's the first time, the player gets some items. Otherwise a message can be prompted stating that the chest has already been looted.






---
description: 'Delta Six, three Tangos ahead. Let them pass or take them down. Your choice.'
---

# Behavior

Despite of the game, creating an AI for a game, even in its most simple form can be a daunting task. Luckily there's a bunch of smart people out there that have developed tools that help create, visualize and organize behavior system.

One of the most widely used system are the **Behavior Trees**, which were used in the first Halo game and popularized it due to its flexibility and power.

{% hint style="info" %}
Although **FSM** \(from now on; _Finite State Machines_\) are easier to understand and more intuitive, they quickly become unmaintainable due to the large amount of connections and dependencies. That's why we've chosen to use **BT** \(_Behavior Trees_ from now on\)
{% endhint %}

## Key Features

* **Node-Based Graph** with auto-arrange capabilities for a maximum comfort
* Only a handful of **nodes** are needed to create any type of AI
* Perception system allows characters to be aware of their surroundings
* Extensible through our **Open API**
* **Live Debug** runtime states right in the Editor.

## Setup

Download the package from the the **Unity Asset Store**. You'll first need to have **Game Creator** installed.

Then, bring up the _Modules Window_ clicking on the Game Creator option in the toolbar. Click the **Behavior** Module **Enable** button.

{% hint style="danger" %}
This module requires **Game Creator** and won't work without it. Don't attempt to extract the package inside the Plugins/ folder as it will throw errors.
{% endhint %}


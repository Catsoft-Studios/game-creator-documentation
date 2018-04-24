---
description: Learn everything Game Creator has to offer
---

# Overview

The heart of **Game Creator** is composed of 6 different components. 

The first three \(**Actions**, **Events** and **Triggers**\) focus on giving you the tools to create gameplay mechanics and design interactive elements. The other three \(**Hotspots**, **Characters** and **Camera Motors**\) act as an interface for the previous ones between the player and interactions.

![\(The Player activates a Trigger when entering the green zone, which calls the Actions sequence\)](../.gitbook/assets/example.jpg)

For example, a user controls a **Character** \(Player\) which when it steps on a **Trigger**, it executes a set of **Actions** \(which can be a trap where rocks fall and reduce the player's HP\)

### Actions

A set of instructions that are sequentially executed from top to bottom. For example, an Actions set could be the following one:

* Move **Player** near object **Chest**
* Play animation `Open` on object **Chest**
* Give `10 gold coins` to **Player**

Click [here](actions.md) to learn more about them.

### Events

Condition the execution of **Actions**. For example, you can check if the object **Chest** has been opened. If so, don't increase the player's `gold coins`, but show the message: `This chest has already been looted!` 

Click [here](events.md) to learn more

### Triggers

Triggers react to inputs and can execute one or more **Actions** and **Events**. For example, you can detect when the player enters a _Lava Zone_ and execute an **Action** that makes the player take damage.

Click [here](triggers.md) to learn more about Triggers.

##   {#high-level-components}


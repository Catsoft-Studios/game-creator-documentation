---
description: You've got questions? We've got some answers!
---

# FAQ

## General



## Game Creator

### What kind of games can I make with Game Creator?

Game Creator is not tied to any specific game genre. You can even create a mobile app that isn't a game with Game Creator. Despite this, we focus all efforts on adventure and action games. Here's an example of a game made with an early version of Game Creator.

### Is Game Creator a Visual Scripting tool?

Game Creator is more than a scripting tool. It's an entire game creator toolbox that handles all the heavy lifting and lets you focus on what matters: Making awesome games. It helps you kickstart the development of your games with just a few seconds. Creating cinematic sequences is extremely easy with our [Camera Motors](game-creator/components/camera/). Our [high-level scripting language](game-creator/components/actions.md) abstracts you from complex math and lets you use simple instructions such as: Move character from A to B. Under the hood, these instructions handle collision avoidance, locomotion, acceleration, inverse kinematics to align the feet to the floor, etc... Check the [Get Started](quickstart/get-started.md) section for a complete list of features.

### Can I make a multiplayer game with Game Creator?

Not at the moment. But we've recently partnered with [Ninjutsu Games](https://assetstore.unity.com/publishers/3171) and they will be developing a module that will allow Game Creator to be used for multiplayer online games.

### Can I use my own scripts with Game Creator?

Yes. Game Creator is all wrapped and isolated in its own namespace. Game Creator has an [open API](game-creator/game-creator-api/) architecture that allows you to extend all functionalities. All logic and data are located inside the [special](https://docs.unity3d.com/Manual/SpecialFolders.html) Plugins/GameCreator/ folder. This means that recompiling your project won't also recompile Game Creator.

### Can I integrate other Unity Asset Store packages with Game Creator?

Absolutely. We actually encourage you to do it! Take for example the Call Method Action. It allows you to call any function from any component \(even custom ones\) with up to one parameter. To make everything even more automatic, we're working on integration modules with the most popular Asset Store packages.




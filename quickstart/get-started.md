# Get Started

**Game Creator** is an ecosystem that gives [Unity](https://unity3d.com) developers a world class technology platform from which they can build games that work seamlessly across multiple platforms quickly and efficiently.

In this pages you'll learn everything you need to start using **Game Creator** like a **PRO**. Alternatively you can watch our [15 minute Quickstart playlist on Youtube](https://www.youtube.com/watch?v=IG8GXAAih2Q&list=PL7FyK0gfdpCbxMrWIV9B2xQiExkiZbpa5).

{% embed data="{\"url\":\"https://www.youtube.com/watch?v=IG8GXAAih2Q&list=PL7FyK0gfdpCbxMrWIV9B2xQiExkiZbpa5\",\"type\":\"video\",\"title\":\"\#1 Getting Started with Game Creator - Overview\",\"description\":\"Download at: https://www.assetstore.unity3d.com/\#!/content/89443\n\nGame Creator is an ecosystem that gives Unity developers a world class technology platform from which they can build games that work seamlessly across multiple platforms quickly and efficiently.\n\nIn these videos you\'ll learn everything you need to start using Game Creator like a PRO.\",\"icon\":{\"type\":\"icon\",\"url\":\"https://www.youtube.com/yts/img/favicon\_144-vfliLAfaB.png\",\"width\":144,\"height\":144,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://i.ytimg.com/vi/IG8GXAAih2Q/maxresdefault.jpg\",\"width\":1280,\"height\":720,\"aspectRatio\":0.5625},\"embed\":{\"type\":\"player\",\"url\":\"https://www.youtube.com/embed/IG8GXAAih2Q?rel=0&showinfo=0\",\"html\":\"<div style=\\"left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.2493%;\\"><iframe src=\\"https://www.youtube.com/embed/IG8GXAAih2Q?rel=0&amp;showinfo=0\\" style=\\"border: 0; top: 0; left: 0; width: 100%; height: 100%; position: absolute;\\" allowfullscreen scrolling=\\"no\\"></iframe></div>\",\"aspectRatio\":1.7778},\"caption\":\"\"}" %}

{% hint style="info" %}
Have any question? Feel free to drop us a line at [hello@catsoft-studios.com](mailto:hello@catsoft-studios.com).
{% endhint %}

## Community Driven

**Game Creator** is a community driven product. That means that you can have a real impact on the direction of the development cycle. We internally have our own roadmap but if there's a community consensus that a certain feature should be implemented first, we hit the _pause_ button and implement that feature.

{% hint style="info" %}
Join our [Discord server](https://discord.gg/ZCkqJf5) for realtime discussions about the development of **Game Creator**.
{% endhint %}

## Why Game Creator?

Because it's a highly flexible tool that does all the heavy lifting of game development so you can focus on what matters: **Making awesome games!**

**Game Creator** comes packed with state-of-the-art components like the **Characters**, which allow you to drag and drop a model and _Wham!_ you have a working player with **walk**, **run** and **jump** controls, **head tracking**, advanced **Inverse Kinematics** for correct feet placement and a bunch of other cool stuff.

### For Artists & Game Designers

If you are a game designer chances are you don't really feel comfortable with code. At let's be honest: Making games involves coding. Like a lot.

Some **Visual Scripting** solutions might ease the road a little bit, but after a couple of hours you end up making a spaghetti code. Game Creator comes with a visual scripting solution with a twist; it's displayed as a node-graph layout but as a vertical list. Each Action is sequentially executed from top to bottom and the next won't start until the previous one has finished.

Each **Action** is a high-level instruction. That means that unlike other scripting solutions, you don't need to deal with trigonometry. For example, when making a character follow the player you would normally need to subtract both positions, then normalize the result to get the direction vector and finally change the character's position by this vector multiplied by a certain speed, multiplied again by `Time.deltaTime`... 

Ew! Boooring! With Game Creator you have an **Action** called `Move Character To` that does that: move a character to a specified destination. Under the hood it does a bunch of things, but that is all transparent to you.

See the [Game Creator Overview](../game-creator/overview/) section for more information on what Game Creator can offer to you.

### For Programmers

If you are a coder you will fall in love with Game Creator's architecture. It's made to be easy to use and extremely extendable. Check our [Extend Game Creator](../game-creator/game-creator-api.md) section to see how you can hack it. Why waste time reinventing the wheel?

Do you have existing coded tools? We're happy to say that they most likely work with Game Creator out of the box.

## About this Documentation

Each Game Creator **module** has its own _Section_. Each _Section_ contains an introduction chapter that overviews the core concepts. It is advised you read first the _Overview_ page. Then you can decide to follow the guide from top to bottom or jump to between sections.

Game Creator is extremely easy to use. Despite this, sometimes certain features might require some extra explanation. Here's how this documentation describes highlights:

{% hint style="info" %}
A **Blue** highlight provides extra information on the current topic.
{% endhint %}

{% hint style="success" %}
A **Green** highlight is used for best practices.
{% endhint %}

{% hint style="warning" %}
An **Orange** highlight will inform of something which can lead to errors or confusion.
{% endhint %}

{% hint style="danger" %}
A **Red** highlight is a critical message that can be game breaking. Read with special care!
{% endhint %}

## Basic Concepts

**Game Creator** provides a set of flexible tools to create any game of any genre. On top of the core tools [Catsoft Studios](https://catsoft-studios.com) and the rest of the community builds **modules** that extend Game Creator's functionalities  adding new features and improving existing ones.

For example, the **Inventory** module give you a set of extremely easy to use tools to create items which produce different effects when consumed. It also allows you to easily define crafting recipes between different items and what happens when these two are combined.

You can manage all your **modules** from the **Module Manager** window \[⌘ + M\]. You can download free modules from the [Game Creator Store](https://store.gamecreator.io).

{% hint style="info" %}
See the [Module Manager](../game-creator/module-manager.md) section for a full list of all the available **modules.**
{% endhint %}


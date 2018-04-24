# Get Started

**Game Creator** is an ecosystem that gives [Unity](https://unity3d.com) developers a world class technology platform from which they can build games that work seamlessly across multiple platforms quickly and efficiently.

In this pages you'll learn everything you need to start using **Game Creator** like a **PRO**. Alternatively you can watch our [15 minute Quickstart playlist on Youtube](https://www.youtube.com/watch?v=IG8GXAAih2Q&list=PL7FyK0gfdpCbxMrWIV9B2xQiExkiZbpa5).

{% hint style="info" %}
Have any question? Feel free to drop us a line at [hello@catsoft-studios.com](mailto:hello@catsoft-studios.com).
{% endhint %}

## Why Game Creator?

Because it's a highly flexible tool that does all the heavy lifting of game development so you can focus on what matters: **Making awesome games!**

### For Artists & Game Designers

If you are a game designer chances are you don't really feel comfortable with code. At let's be honest: Making games involves coding. Like a lot.

Some **Visual Scripting** solutions might ease the road a little bit, but after a couple of hours you end up making a spaghetti code. Game Creator comes with a visual scripting solution with a twist; it's displayed as a node-graph layout but as a vertical list. Each Action is sequentially executed from top to bottom and the next won't start until the previous one has finished.

Each **Action** is a high-level instruction. That means that unlike other scripting solutions, you don't need to deal with trigonometry. For example, when making a character follow the player you would normally need to subtract both positions, then normalize the result to get the direction vector and finally change the character's position by this vector multiplied by a certain speed, multiplied again by `Time.deltaTime`... 

Ew! Boooring! With Game Creator you have an **Action** called `Move Character To` that does that: move a character to a specified destination. Under the hood it does a bunch of things, but that is all transparent to you.

See the [Game Creator Overview](../game-creator/game-creator-overview.md) section for more information on what Game Creator can offer to you.

### For Programmers

If you are a coder you will fall in love with Game Creator's architecture. It's made to be easy to use and extremely extendable. Check our [Extend Game Creator]() section to see how you can hack it. Why waste time reinventing the wheel?

Do you have existing coded tools? We're happy to say that they most likely work with Game Creator out of the box.

## About this Documentation

Each Game Creator **module** has its own _Section_. Each _Section_ contains an introduction chapter that overviews the core concepts. It is advised you read first the _Overview_ page. Then you can decide to follow the guide from top to bottom or jump to between sections.

Game Creator is extremely easy to use. Despite this, sometimes certain features might require some extra explanation. Here's how this documentation describes highlights:

{% hint style="info" %}
A **blue** highlight provides extra information on the current topic.
{% endhint %}

{% hint style="success" %}
A **green** highlight is used for best practices.
{% endhint %}

{% hint style="warning" %}
An **orange** highlight will inform of something which can lead to errors or confusion.
{% endhint %}

{% hint style="danger" %}
A **red** highlight is a critical message that can be game breaking. Read with special care!
{% endhint %}

## Basic Concepts

**Game Creator** provides a set of flexible tools to create any game of any genre. On top of the core tools [Catsoft Studios](https://catsoft-studios.com) and the rest of the community builds **modules** that extend Game Creator's functionalities  adding new features and improving existing ones.

For example, the **Inventory** module give you a set of extremely easy to use tools to create items which produce different effects when consumed. It also allows you to easily define crafting recipes between different items and what happens when these two are combined.

You can manage all your **modules** from the **Module Manager** window \[⌘ + M\]. You can download free modules from the [Game Creator Store](https://store.gamecreator.io).

{% hint style="info" %}
See the [Module Manager](../game-creator/module-manager.md) section for a full list of all the available **modules.**
{% endhint %}


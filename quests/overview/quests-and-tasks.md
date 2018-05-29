# Quests & Tasks

Before getting hands on creating Quests and tasks, let's first review a few key concepts.

* **Quests:** Quests are any objective the player \(or any other entity\) has to do in order to change its state. When using the word Quests we both reference **Quest Roots** and **Tasks**.
* **Quest Root:** A Quest Root is the top-level quest that summarizes the entire chain of tasks.
* **Task:** A Task is anything below a Quest Root which defines one single goal. A Task can have any number of children Tasks as well as any number of siblings.

![\(Quests, Quest Roots and Tasks\)](../../.gitbook/assets/quests-types.jpg)

At a given time, a **Quest** element \(**Quest Root** or **Task**\) can be at one and only one of the following states:

* **Inactive:** Default state for any Quest.
* **Active:** The Quest has been discovered
* **Complete:** The Quest has been successfully fulfilled.
* **Failed:** The Quest has failed
* **Abandoned:** The Quest was abandoned. Failed and Abandoned trigger the same effects.

{% hint style="success" %}
It is important to note that a Complete Quest can't be directly transitioned to Failed. There's a transition dependency from which states one Quest can be transitioned to.
{% endhint %}

![](../../.gitbook/assets/quests-graph.jpg)

{% hint style="info" %}
Quest Roots can also be marked as **Tracking**. This will allow the **Journal** and other systems to know which quests are the ones being tracked by the player.
{% endhint %}

Apart from the Status and the isTracking property, a Quest also has the following attributes:

* **Title:** A localizable text that serves as the Quest Root/Task title.
* **Description:** A text that contains further details on the Quest. Also localizable.
* **Sprite:** This is completely optional. Some Quests might need to reference a map, a picture or simply have an icon that defines the type of quest. Here you can set it.

Because any **Quest** \(**Root Quest** or **Task**\) can be either **Completed** or **Failed** \(aka **Abandoned**\) it is possible to also assign Actions that will be automatically triggered when transitioning to one of these states.

![](../../.gitbook/assets/quest-settings.jpg)




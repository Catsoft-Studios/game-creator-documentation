---
description: Where we are. Where we go. How did we do.
---

# Roadmap

![](.gitbook/assets/roadmap.jpg)

Welcome to the Game Creator roadmap. We hope to keep this page up to date with the latest news about the development direction of our product.

Each year is divided into 3 quarters. Each quarter is a milestone and has a collection of states. In each state we include epics/tasks that must be done.

* Past quarters have no states.
* Current quarter tasks can be **Active** or **Delayed**.
* Future quarters have no states

At the end of each quarter we'll include a small [postmortem](https://en.wikipedia.org/wiki/Postmortem_documentation) where we'll share insights of what went right and what went wrong during the development cycle. This will be very useful for both us and you.

{% hint style="warning" %}
**Game Creator** is a community driven product. Our primary goal is to provide you with stable and reliable releases. As such, any indications of target release dates and features listed are subject to change.
{% endhint %}

{% hint style="info" %}
Join our [Discord server](https://discord.gg/ZCkqJf5) and let's discuss the development of Game Creator!
{% endhint %}

## 2018 - Milestones

{% tabs %}
{% tab title="Q1" %}
* [x] Game Creator - New Variable System
* [x] Game Creator - Module Manager 2.0
* [x] Dialogue module
* [x] Game Creator Store 2.0
* [ ] Quest module
{% endtab %}

{% tab title="Postmortem" %}
### What went right

* We managed to complete the Dialogue system without critical issues
* The new Module Manager and the dependency system
* Use Firebase as our backend service provider
* The Module Manager automatic build/deploy function settings.
* Splitting Game Creator into data-logic components

### What went wrong

* Too much time spent in re-coding existing things \(Module Manager, Variables, ...\)
* Releases weren't properly tested and we shipped way too much patch releases
* Low release of video tutorials
* Still no alpha release channel
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Q2" %}
### Active

* [ ] Quest module
* [ ] Shooter module
* [ ] Stats/Attributes module
* [ ] Game Creator - Enhance Save/Load system
* [ ] Game Creator - Gestures with Avatar Masks
* [ ] Game Creator - Limb IK targets
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Q3" %}
TBA
{% endtab %}
{% endtabs %}

## 2017 - Milestones

{% tabs %}
{% tab title="2017" %}
* [x] Game Creator - Release
* [x] Game Creator Store 1.0
* [x] Game Creator Homepage
* [x] Inventory module
* [ ] Dialogue module
{% endtab %}

{% tab title="Postmortem" %}
### What went right

* Releasing Game Creator within the expected deadline. 
* Effectively communicate what Game Creator is. 
* Releasing the Inventory module within the expected deadline.
* Using GitLab CI/CD to automatically deploy new Store modules.
* Using Jekyll as the bare bone structure for our website.
* Using short video tutorials.

### What went wrong

* Actions & Conditions architecture. Using Scriptable Objects and attaching them to the scene asset resulted in too many edge cases when creating prefabs or duplicating.
* The Module Manager 1.0 static architecture
* The Variable system was too constrained and did only accept primitive types.
* We couldn't release the Dialogue module within the expected deadline.
{% endtab %}
{% endtabs %}




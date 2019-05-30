# Roadmap

![](../.gitbook/assets/roadmap.jpg)

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
Join our [Discord server](https://gamecreator.page.link/discord) and let's discuss the development of Game Creator!
{% endhint %}

## 2019 - Milestones

{% tabs %}
{% tab title="Q3" %}
* [ ] Melee module
* [ ] Integration modules
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Q2" %}
* [ ] Shooter module
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Q1" %}
* [x] Behavior module
* [x] Update Quickstart tutorials
* [ ] Shooter module
* [ ] Melee module
{% endtab %}

{% tab title="Postmortem" %}
### What went right

* The Behavior module went much better than expected
* The Behavior module was done within the time frame

### What went wrong

* Unrealistic number of modules were set for the first quarter
* Some Game Creator updates could have been handled better
{% endtab %}
{% endtabs %}

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
* Use Firebase as our backend
* The Module Manager automatic build/deploy.
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

* [x] Quest module
* [ ] Shooter module
* [ ] Stats/Attributes module
* [x] Game Creator - Enhance Save/Load system
* [x] Game Creator - Gestures with Avatar Masks
* [x] Game Creator - Limb IK targets
{% endtab %}

{% tab title="Postmortem" %}
### What went right

* Deploying the Quests modules before releasing to the Asset Store
* Enhancing the Save/Load system to almost automatically save play-throughs
* Many brainstorm sessions to architect the Stats module

### What went wrong

* Vacations split the development of the Stats module
* Game Creator update took too much time, though brought many new features
* The Stats module wasn't 100% architected when the development started
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Q3" %}
* [x] Stats module
* [x] Game Creator Hub
* [ ] Shooter module
* [ ] Integration with Cinemachine
* [ ] Integration with Bolt
* [ ] Integration with Playmaker
{% endtab %}

{% tab title="Postmortem" %}
### What went right

* Completed Game Creator Hub with admin dashboard
* Improved Game Creator stability a lot
* Kept documentation up to date
* Stats module design and examples work great

### What went wrong

* Poor communication with _Beta_ phase ending
* Marketing is still a thing that needs to be worked out
* Did not hit integration modules deadline
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




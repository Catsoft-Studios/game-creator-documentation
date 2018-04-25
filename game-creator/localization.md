---
description: Hello! Hola! Bonjour! Ciao! Salaam! Konnichiwa!
---

# Localization

The **Localization Tools** were first added in version **0.2.4**

Video games are international products and it would be a big mistake to think that shipping a game in only one language \(_English_, for example\) is enough. Luckily, **Game Creator** comes with built-in **Localization tools** that simplify the process of translating a game into multiple languages.

{% hint style="info" %}
We've designed the **Localization tools** to be as simple as possible and non-intrusive in your development workflow. 

The last thing we wanted to do was to display 5 different input fields, each for a different languages, for each localized message.
{% endhint %}

## Localized Strings {#localized-strings}

Localized string fields are composed of two parts. The first is the _input field_. Here you type the text in the default language. For example, if we want to show a message saying _Hello, World!_ we would simply type these characters there.

The second part is a button that enables/disables the translation. If you want the previous text to be localized, simply enable the _Kanji_ character and you'll be good to go.

There's a third component named _Post Process_. This is an extra tool that allows you to post process the text displayed. The available options are:

* **None** - Default option. Does no post-process.
* **First Uppercase** - Changes the first character \(not symbol\) to uppercase.
* **Title Case** - Changes all the first characters in each word to uppercase.
* **All Uppercase** - Changes all characters to uppercase.
* **All Lowercase** - Changes all characters to lowercase.

But where do you actually specify the translations? That's done inside the _Preferences Menu_. Press ⌘ + _P_ or click on `Game Creator `→` Preferences` to open the menu and navigate to **Localization**.

The **Localization** tab has two sections: **Languages** and **Texts**.

### Languages {#languages}

Here you can add new languages and export and import the translations. For example, continuing the previous example, let's say we want to add the _Spanish_ language and translate the previous message.

All you need to do is to click the **+** symbol and select the _Spanish_ language. Then, click on **Export...** and select where you want to save the translation document. Translation documents are in _JSON_ format.

If you open the saved document you'll see that there's only one entry with the text "_Hello, World!_". This is what needs to be translated. Let's change it to "_Hola, Mundo!_", save and close the document.

To update a language click on **Import...** and select the saved file. If everything is correct, the message _Last Update_ will be updated to the current time. If something happened, an error message will be prompted in the console window.

To test that everything works, create a new **Action** and use the **Change Language** to select _Spanish_.

{% hint style="info" %}
When changing the language in runtime, all texts are updated instantaneously in **realtime**. There's no need to restart the application or reload the scene.
{% endhint %}

### Texts {#texts}

These are all the texts that can be translated. Notice that if you remove a Game Object that contained a component with a localized string it might not disappear from this list, so it is a good practice to review these strings and delete those that are unused, from time to time.

## Best Practices {#best-practices}

* Don't set any text as translatable until the very end of the project. You can always do that later.
* Keep a copy of all translation documents or save them inside the project. better yet, use _git_ to keep older copies.
* Use the **Post Process** tool to transform the output of the text to fit your game. That way, translators don't need to keep in mind what should be written in capital letters and what not.
* Regularly check the texts from the _Texts_ tab. Sometimes some texts that have been removed bypass **Game Creator**'s detection and still appear.


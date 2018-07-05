# Custom Module

**Game Creator** comes with a dependency manager called **Module Manager**. It allows to add, remove and seamlessly update extensions that add new features to our core product.

{% hint style="info" %}
Learn more about the Module Manager [here](../tools/module-manager.md).
{% endhint %}

All Modules are located at `Plugins/GameCreatorData/Modules/`. Modules are identified by a **unique name** or **bundleID**. You can name bundles however you want, but we recommend following the pattern:

```text
com.[company].[product-type].[product-name]
```

For example, the **bundleID** of the **Dialogue** module is `com.gamecreator.module.dialogue`. By using convention it's easier to avoid duplicate names. 

## Anatomy of a Module

A module is composed of two files. The **Unity Package** and the **Manifest** file.

The **Unity Package** contains all the assets and scripts of the module. It also knows where the files should be routed when updating or installing the module.

{% hint style="info" %}
If you are unfamiliar with [package managers](https://en.wikipedia.org/wiki/Package_manager), imagine the **Unity Package** is a **zip** file you can decompress to access its content.
{% endhint %}

The Manifest file contains the rest of the information relative to the specific module. Manifest files are password protected so that inexperienced users don't accidentally mess with them.

{% hint style="success" %}
The password of all Manifest files is **gamecreator** \(lowercase and without any spaces\).
{% endhint %}

![\(Example of Manifest file\)](../../.gitbook/assets/custom-mm-manifest.png)

After signing in the Manifest file you'll see all the Manifest options.

![\(Custom Manifest file with testing values\)](../../.gitbook/assets/custom-mm-manifest-file.png)

The Manifest can be broken down into 3 sections.

* The **Build Module** and **Logout** options.
* The **General Information**.
* The **Build Settings**.

### Build Module

The **Build Module** button allows you to pack the module into a `bundleid.unitypackage` file which can be found next to the **Manifest**.

{% hint style="warning" %}
The **Build Module** option will overwrite any existing Unity Package at that location.
{% endhint %}

The **Logout** option allows you to exit the Manifest editing mode.

### General Information

The General information includes the **Information**, **Version**, **Author**, **Dependencies** and **Tags** information.

#### Information

Here you can modify the **name**, **description** and **bundle id** and more. You can freely alter any of these fields \(but bundle-id\) without any further consequences.

#### Version

The version system is an incremental number. We follow the [Semantic Versioning 2.0 standard](https://semver.org/). This means that version are composed of three fields: **X.Y.Z** where

* **X** - Major version. Complete overhaul of major systems.
* **Y** - Minor version. New features are added. Might need to take some config steps when upgrading.
* **Z** - Patch version. Does not contain new features. Fixes errors from the last minor version.

{% hint style="danger" %}
On top of this, stable versions always start at **1.0.0**. A **major** version of **0** means that product is in **Beta** or **Alpha** phase and should not be used in production.
{% endhint %}

#### Author

Information about the creator of this module. Used for support inquiries.

#### Dependencies

Here you can list what modules are required to be installed before this module. You can also specify the minimum compatible version.

{% hint style="info" %}
Unless the **minimum dependency** requirements are met, a module won't be neither **installable** nor **updatable**.
{% endhint %}

#### Tags

Tags allow the module to be easily searched.

### Build Settings

The **Build Settings** are the most important part of the **Module Manifest**. They tell which parts are included in the package and which aren't.

Since version 0.5.1 **Game Creator** assets are split in two: The **Logic** and the **Data**.

The **Logic** includes scripts and all the assets that must be shipped with **Game Creator** in order to work. A module must always include at least one asset \(either a script, a 3D model, ...\).

The **Data** is usually auto-generated information, such as script instances. **Data** is usually excluded from the build as it would overwrite other user's existing data.

{% hint style="info" %}
**Data** is usually used when building an [Example](https://store.gamecreator.io/?tags=examples) module, which needs previously auto-generated data.
{% endhint %}

In **Game Creator** we publish all the **Logic** at `Assets/Plugins/GameCreator` directory and the **Data** inside `Assets/Plugins/GameCreatorData`.


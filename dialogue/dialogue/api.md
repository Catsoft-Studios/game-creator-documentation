---
description: exec Dialogue.sh << script.txt >> output.log
---

# API

To manually start a **Dialogue** is as easy as calling the **`Run`** method from the **Dialogue** component. Bear in mind though that this method is a _coroutine_.

{% hint style="info" %}
More information about _coroutines_ [here](https://docs.unity3d.com/Manual/Coroutines.html).
{% endhint %}

```csharp
StartCoroutine(this.dialogue.Run());
```

The previous example shows how to start a conversation between characters. We provide a _coroutine_ so that you can keep track when the conversation finishes. For example:

```csharp
public IEnumerator StartDialogue()
{
    Debug.Log("Start Dialogue!");
    yield return this.dialogue.Run();
    Debug.Log("Dialogue finished!");
}
```

Thanks to the power of _coroutines_, we can hold the execution of the **`StartDialogue`** method and resume it once the **Dialogue** is finished.


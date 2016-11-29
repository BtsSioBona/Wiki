* Pour tester plusieurs champs et vérifier s'ils sont nuls ou non plutôt que de les tester un par un.

```c#
  var myStrings = new List<string> {string1, string2, string3, string4};
    if (!(myStrings.All(s => s == null)))
    {
      // CODE
    }
    else // CODE
```

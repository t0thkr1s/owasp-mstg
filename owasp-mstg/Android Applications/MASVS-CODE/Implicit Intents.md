#MASVS-CODE-4 

Check AndroidManifest.xml and look for Intent blocks. Any system actions?

```java
Intent intent = new Intent(); intent.setAction("android.intent.action.GET_CONTENT"); startActivityForResult(Intent.createChooser(intent, ""), REQUEST_IMAGE);
```

Check how the return value of the intent is handled by looking for the `onActivityResult` callback. If the return value of the intent isn't properly validated, an attacker may be able to read arbitrary files or execute arbitrary code from the app's internal `/data/data/' storage.

- [ ] Check

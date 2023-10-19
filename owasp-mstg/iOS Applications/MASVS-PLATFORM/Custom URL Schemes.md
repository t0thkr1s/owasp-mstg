#MASVS-PLATFORM-1 

In a compiled application (or IPA), registered protocol handlers are found in the file `Info.plist` in the app bundle's root folder. Open it and search for the `CFBundleURLSchemes` key, if present, it should contain an array of strings.

Search for deprecated methods like:

- `application:handleOpenURL:`
- `openURL:`
- `application:openURL:sourceApplication:annotation:`

```shell
rabin2 -zzq Telegram\ X.app/Telegram\ X | grep -i "openurl"
```

If you simply want to open the URL scheme you can do it using Frida:

```
$ frida -U iGoat-Swift
[iPhone::iGoat-Swift]-> function openURL(url) { var UIApplication = ObjC.classes.UIApplication.sharedApplication(); var toOpen = ObjC.classes.NSURL.URLWithString_(url); return UIApplication.openURL_(toOpen); } [iPhone::iGoat-Swift]-> openURL("tel://234234234") true
```

or use the Notes application.

- [ ] Check
#MASVS-PLATFORM-1 

### Checking the Associated Domains Entitlement

```xml
<key>com.apple.developer.associated-domains</key>
<array>
	<string>applinks:telegram.me</string>
	<string>applinks:t.me</string>
</array>
```

### Checking if the App is Calling Other App's Universal Links

If you don't have the original source code, search in the symbols and in the strings of the app binary. For example, we will search for Objective-C methods that contain "openURL":

```shell
rabin2 -zq Telegram\ X.app/Telegram\ X | grep openURL
0x1000dee3f 50 49 application:openURL:sourceApplication:annotation:
0x1000dee71 29 28 application:openURL:options:
0x1000df2c9 9 8 openURL:
0x1000df772 35 34 openURL:options:completionHandler:
```

- [ ] Check
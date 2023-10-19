#MASVS-PLATFORM-1

Inspect all _purpose strings Info.plist keys_, usually ending with `UsageDescription`:

```xml
<plist version="1.0">
	<dict>
		<key>NSLocationWhenInUseUsageDescription</key>
		<string>Your location is used to provide turn-by-turn directions to your destination.</string>
```

For each purpose string in the `Info.plist` file, check if the permission makes sense.

- [ ] Check
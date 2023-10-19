If you don't have the original IPA, then you need a jailbroken device where you will install the app (e.g. via App Store). Once installed, you need to extract the app binary from memory and rebuild the IPA file. Because of DRM, the app binary file is encrypted when it is stored on the iOS device, so simply pulling it from the Bundle (either through SSH or Objection) will not be sufficient to reverse engineer it.

## CLUTCH

Build [Clutch](https://mas.owasp.org/MASTG/Tools/0x08a-Testing-Tools/#clutch) as explained on the Clutch GitHub page and push it to the iOS device through `scp`. Run Clutch with the `-i` flag to list all installed applications:

```
root# ./Clutch -i
2019-06-04 20:16:57.807 Clutch[2449:440427] command: Prints installed applications Installed apps: ... 5: Telegram Messenger <ph.telegra.Telegraph> ...
```

Once you have the bundle identifier, you can use Clutch to create the IPA:

```
root# ./Clutch -d ph.telegra.Telegraph
2019-06-04 20:19:28.460 Clutch[2450:440574] command: Dump specified bundleID into .ipa file ph.telegra.Telegraph contains watchOS 2 compatible application. It's not possible to dump watchOS 2 apps with Clutch (null) at this moment. Zipping Telegram.app 2019-06-04 20:19:29.825 clutch[2465:440618] command: Only dump binary files from specified bundleID ... Successfully dumped framework TelegramUI! Zipping WebP.framework Zipping NotificationContent.appex Zipping NotificationService.appex Zipping Share.appex Zipping SiriIntents.appex Zipping Widget.appex DONE: /private/var/mobile/Documents/Dumped/ph.telegra.Telegraph-iOS9.0-(Clutch-(null)).ipa Finished dumping ph.telegra.Telegraph in 20.5 seconds
```

## FRIDA-IOS-DUMP

First, make sure that the configuration in [Frida-ios-dump](https://mas.owasp.org/MASTG/Tools/0x08a-Testing-Tools/#frida-ios-dump) `dump.py` is set to either localhost with port 2222 when using [iproxy](https://mas.owasp.org/MASTG/Tools/0x08a-Testing-Tools/#iproxy), or to the actual IP address and port of the device from which you want to dump the binary. Next, change the default username (`User = 'root'`) and password (`Password = 'alpine'`) in `dump.py` to the ones you use.

Now you can safely use the tool to enumerate the apps installed:

```
$ python dump.py -l
PID Name Identifier
---- --------------- -------------------------------------
860 Cydia com.saurik.Cydia
1130 Settings com.apple.Preferences
685 Mail com.apple.mobilemail
834 Telegram ph.telegra.Telegraph
```

and you can dump one of the listed binaries:

```
$ python dump.py ph.telegra.Telegraph

Start the target app ph.telegra.Telegraph
Dumping Telegram to /var/folders/qw/gz47_8_n6xx1c_lwq7pq5k040000gn/T
[frida-ios-dump]: HockeySDK.framework has been loaded.
[frida-ios-dump]: Load Postbox.framework success. 
[frida-ios-dump]: libswiftContacts.dylib has been dlopen.
```
#MASVS-PLATFORM-1 

If you only have the compiled/installed app, try searching for the previous method and property, for example:

```shell
$ rabin2 -zq Telegram\ X.app/Telegram\ X | grep -i activityItems 0x1000df034 45 44 initWithActivityItems:applicationActivities:
```

[[Inspect Send Activity Data]]

```
frida -U APP -l inspect_send_activity_data.js
```

- [ ] Check
#MASVS-STORAGE-2 


```shell
~/Library/Application Support/MobileSync/Backup/<UDID>
```

```shell
grep -iRn "password" .
```

To identify if a backup is encrypted, you can check the key named "IsEncrypted" from the file "Manifest.plist", located at the root of the backup directory. The following example shows a configuration indicating that the backup is encrypted:

```xml
<?xml version="1.0" encoding="UTF-8"?> <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> <plist version="1.0"> ... <key>Date</key> <date>2021-03-12T17:43:33Z</date> <key>IsEncrypted</key> <true/> ... </plist>
```

For inspecting backups, we can use iMazing: https://imazing.com

- [ ] Check

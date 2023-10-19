#MASVS-STORAGE-2

# LOGCAT

```
adb logcat | grep "$(adb shell ps | grep PACKAGE | awk '{print $2}')"
```

- [ ] Check


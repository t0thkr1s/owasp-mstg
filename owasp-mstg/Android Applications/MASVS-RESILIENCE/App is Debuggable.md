#MASVS-RESILIENCE-4 

# CHECK MANIFEST

```xml
<application android:debuggable="true" android:icon="@drawable/ic_launcher" android:label="@string/app_name" android:theme="@style/AppTheme">
```

# ADB

```
adb shell dumpsys package PACKAGE | grep -c "DEBUGGABLE"
2
```

- [ ] Check
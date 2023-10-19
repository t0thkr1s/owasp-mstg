#MASVS-RESILIENCE-4 

Inspect the app entitlements and check the value of `get-task-allow` key. If it is set to `true`, the app is debuggable.

```
codesign -d --entitlements - APP.app
```

```
ldid -e APP.app/APP
```

- [ ] Check
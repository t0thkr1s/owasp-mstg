#MASVS-CODE-2 

Check if the app has support for in-app updates and validate if it's properly enforced so that the user is not able to continue using the app without updating it first.

```java
//Part 1: check for update // Creates instance of the manager.
AppUpdateManager appUpdateManager = AppUpdateManagerFactory.create(context); // Returns an intent object that you use to check for an update. 
Task<AppUpdateInfo> appUpdateInfo = appUpdateManager.getAppUpdateInfo();
```

- [ ] Check
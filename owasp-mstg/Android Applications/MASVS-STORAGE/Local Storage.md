#MSVS-STORAGE-1 


# CHECK STRINGS.XML

```xml
<resources>
<string name="app_name">SuperApp</string>
<string name="hello_world">Hello world!</string>
<string name="action_settings">Settings</string>
<string name="secret_key">My_Secret_Key</string>
</resources>
```

Install and use the app, executing all functions at least once. Data can be generated when entered by the user, sent by the endpoint, or shipped with the app.

- Check both internal and external local storage for any files created by the application that contain sensitive data.

- Identify development files, backup files, and old files that shouldn't be included with a production release.

- Check the permissions of the files in `/data/data/<package-name>`. Only the user and group created when you installed the app (e.g., u0_a82) should have user read, write, and execute permissions (`rwx`). Other users should not have permission to access files, but they may have execute permissions for directories.

# SQLITE DATABASES

This should be encrypted...

```
/data/data/PACKAGE/databases
```

# SHARED PREFERENCES

This also should be encrypted...

```
/data/data/PACKAGE/shared_prefs
```

# FIREBASE DATABASE

```
https://_firebaseProjectName_.firebaseio.com/.json
```

- [ ] Check


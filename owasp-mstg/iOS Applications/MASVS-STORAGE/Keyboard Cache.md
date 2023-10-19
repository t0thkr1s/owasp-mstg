#MASVS-STORAGE-2 

If a jailbroken iPhone is available, execute the following steps:

1. Reset your iOS device keyboard cache by navigating to `Settings > General > Reset > Reset Keyboard Dictionary`.
2. Use the application and identify the functionalities that allow users to enter sensitive data.
3. Dump the keyboard cache file with the extension `.dat` in the following directory and its subdirectories. (which might be different for iOS versions before 8.0): `/private/var/mobile/Library/Keyboard/`
4. Look for sensitive data, such as username, passwords, email addresses, and credit card numbers. If the sensitive data can be obtained via the keyboard cache file, the app fails this test.

If you must use a non-jailbroken iPhone:

1. Reset the keyboard cache.
2. Key in all sensitive data.
3. Use the app again and determine whether autocorrect suggests previously entered sensitive information.

- [ ] Check
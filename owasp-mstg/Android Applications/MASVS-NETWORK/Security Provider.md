#MASVS-NETWORK-1 

Applications based on the Android SDK should depend on GooglePlayServices. For example, in the gradle build file, you will find `compile 'com.google.android.gms:play-services-gcm:x.x.x'` in the dependencies block. You need to make sure that the `ProviderInstaller`class is called with either `installIfNeeded` or `installIfNeededAsync`. `ProviderInstaller`needs to be called by a component of the application as early as possible. Exceptions thrown by these methods should be caught and handled correctly.

- [ ] Check
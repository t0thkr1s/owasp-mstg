#MASVS-PLATFORM-1 

When testing Pending Intents you must ensure that they are immutable and that the app explicitly specifies the exact package, action, and component that will receive the base intent. To identify vulnerable implementations, static analysis can be performed by looking for API calls used for obtaining a `PendingIntent`.

## IMPLICIT BASE INTENT

```java
Intent viewIntent = new Intent(Intent.ACTION_VIEW) .setFlags(Intent.FLAG_ACTIVITY_NEW_TASK | Intent.FLAG_GRANT_READ_URI_PERMISSION) .setDataAndType(uri, "video/mp4"); //Implicit Intent
```

## MUTABEL PENDINGINTENT

```java
.setContentIntent(PendingIntent.getActivity( this, REQUEST_CODE, viewIntent, Intent.FLAG_GRANT_READ_URI_PERMISSION)) // Mutable PendingIntent.
```

- [ ] Check

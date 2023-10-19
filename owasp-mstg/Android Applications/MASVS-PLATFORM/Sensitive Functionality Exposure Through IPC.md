#MASVS-PLATFORM-1 

Start by looking at the AndroidManifest.xml, where all activities, services, and content providers included in the app must be declared.

Check for exported broadcast receivers, services, activities and content providers. Try sending malicious input 
## DROZER

```
run app.broadcast.sniff --action BROADCAST
```

- [ ] Check
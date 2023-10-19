#MASVS-PLATFORM-3 

Check for sensitive data displayed in the application switcher. The solution is to set these flags:

```java
getWindow().setFlags(WindowManager.LayoutParams.FLAG_SECURE, WindowManager.LayoutParams.FLAG_SECURE); setContentView(R.layout.activity_main);
```

- [ ] Check
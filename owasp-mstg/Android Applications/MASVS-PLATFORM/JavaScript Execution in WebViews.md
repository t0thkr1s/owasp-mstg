#MASVS-PLATFORM-2 

To test for JavaScript execution in WebViews check the app for WebView usage and evaluate whether or not each WebView should allow JavaScript execution. If JavaScript execution is required for the app to function normally, then you need to ensure that the app follows the all best practices.

```java
webview.getSettings().setJavaScriptEnabled(true);
```

Certificate pinning? XSS, MITM?

- [ ] Check
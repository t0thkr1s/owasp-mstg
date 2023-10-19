#MASVS-PLATFORM-2 

Check the app for WebViews having JavaScript enabled and determine whether the WebView is creating any JavaScript interfaces aka. "JavaScript Bridges". Finally, check whether an attacker could potentially inject malicious JavaScript code.

With access to the JavaScript code, via, for example, stored XSS or a MITM attack, an attacker can directly call the exposed Java methods.

```java
WebView webview = new WebView(this); WebSettings webSettings = webview.getSettings(); webSettings.setJavaScriptEnabled(true); MSTG_ENV_008_JS_Interface jsInterface = new MSTG_ENV_008_JS_Interface(this); myWebView.addJavascriptInterface(jsInterface, "Android"); myWebView.loadURL("http://example.com/file.html"); setContentView(myWebView);
```

- [ ] Check
#MASVS-PLATFORM-2 

Inspect all APIs related to WebView data deletion and try to fully track the data deletion process.

```kotlin
CookieManager.getInstance().removeAllCookies(null) WebStorage.getInstance().deleteAllData() // Clears all storage currently being used by the JavaScript storage APIs. This includes the Application Cache, Web SQL Database and the HTML5 Web Storage APIs.
val webViewDatabase = WebViewDatabase.getInstance(context) // It isn't entirely clear how this differs from WebView.clearFormData() @Suppress("DEPRECATION") webViewDatabase.clearFormData() // Clears any saved data for web forms. 
webViewDatabase.clearHttpAuthUsernamePassword() deleteContentFromKnownLocations(context) // calls FileUtils.deleteWebViewDirectory(context) which deletes all content in "app_webview".
```

- [ ] Check
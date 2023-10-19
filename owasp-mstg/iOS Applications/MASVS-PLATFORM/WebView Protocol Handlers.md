#MASVS-PLATFORM-2 

If a WebView is loading content from the app data directory, users should not be able to change the filename or path from which the file is loaded, and they shouldn't be able to edit the loaded file.

This is a vulnerable UIWebView:

```swift
let scenario2HtmlPath = Bundle.main.url(forResource: "web/UIWebView/scenario2.html", withExtension: nil) do { let scenario2Html = try String(contentsOf: scenario2HtmlPath!, encoding: .utf8) uiWebView.loadHTMLString(scenario2Html, baseURL: nil) } catch {}
```

Search for it like this:

```shell
rabin2 -zz ./WheresMyBrowser | grep -i "loadHTMLString"
```

```shell
rabin2 -zz ./WheresMyBrowser | grep -i "loadFileURL"
```

Using Frida:

```shell
frida-trace -U "APP" -m "*[WKWebView *loadHTMLString*]" -m "*[* URLForResource:withExtension:]"
```

```shell
frida -U -f APP_PACKAGE -l webviews_inspector.js
```

- [ ] Check
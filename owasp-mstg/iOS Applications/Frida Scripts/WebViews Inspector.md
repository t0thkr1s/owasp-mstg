
```js
ObjC.choose(ObjC.classes['WKWebView'], {
    onMatch: function(wk) {
        console.log('onMatch: ', wk);
        console.log('URL: ', wk.URL().toString());
        console.log('javaScriptEnabled: ', wk.configuration().preferences().javaScriptEnabled());
        console.log('allowFileAccessFromFileURLs: ', wk.configuration().preferences().valueForKey_('allowFileAccessFromFileURLs').toString());
        console.log('hasOnlySecureContent: ', wk.hasOnlySecureContent().toString());
        console.log('allowUniversalAccessFromFileURLs: ', wk.configuration().valueForKey_('allowUniversalAccessFromFileURLs').toString());
    },
    onComplete: function() {
        console.log('done for WKWebView!');
    }
});
```
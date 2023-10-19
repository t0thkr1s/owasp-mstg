
```js
setTimeout(function() {
    Java.perform(function() {
        console.log("[*] Script loaded") var Proxy = Java.use("<package-name>.<class-name>") Proxy.isProxySet.overload().implementation = function() {
            console.log("[*] isProxySet function invoked") return false
        }
    });
});
```
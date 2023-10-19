
```js
const UIPasteboard = ObjC.classes.UIPasteboard;
const Pasteboard = UIPasteboard.generalPasteboard();
var items = "";
var count = Pasteboard.changeCount().toString();

setInterval(function() {
    const currentCount = Pasteboard.changeCount().toString();
    const currentItems = Pasteboard.items().toString();

    if (currentCount === count) {
        return;
    }

    items = currentItems;
    count = currentCount;

    console.log('[* Pasteboard changed] count: ' + count +
        ' hasStrings: ' + Pasteboard.hasStrings().toString() +
        ' hasURLs: ' + Pasteboard.hasURLs().toString() +
        ' hasImages: ' + Pasteboard.hasImages().toString());
    console.log(items);

}, 1000 * 5);
```
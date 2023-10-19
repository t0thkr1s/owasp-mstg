#MASVS-PLATFORM-1 

## CHECK MANIFEST

Is there any exposed exported content providers?

## TESTING CONTENT PROVIDERS WITH DROZER

```
run app.provider.info -a PACKAGE
```

```
run scanner.provider.finduris -a PACKAGE
```

```
run app.provider.query content://PACKAGE.CLASS/URI/ --vertical
```

## FINDING INJECTION POINTS

```
run scanner.provider.injection -a PACKAGE
```

```
run scanner.provider.traversal -a PACKAGE
```

- [ ] Check
#MASVS-NETWORK-1 

Make sure that the app:

- verifies the challenge type and the host name and credentials when performing server trust evaluation.
- doesn't ignore TLS errors.
- doesn't use any insecure TLS configurations

The following snippet shows a **vulnerable example** of an app disabling ATS restrictions globally.

```xml
<key>NSAppTransportSecurity</key>
<dict>
	<key>NSAllowsArbitraryLoads</key>
	<true/>
</dict>
```
## Testing for Cleartext Traffic

- Configuring ATS to enable cleartext traffic by setting the `NSAllowsArbitraryLoads` attribute to `true` (or `YES`) on `NSAppTransportSecurity` in the app's `Info.plist`.

- [ ] Check
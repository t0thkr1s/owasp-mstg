#MASVS-NETWORK-2 

## Network Security Configuration

Inspect the Network Security Configuration looking for any `<pin-set>` elements. Check their `expiration` date, if any. If expired, certificate pinning will be disabled for the affected domains.

## TrustManager

```java
final static HostnameVerifier NO_VERIFY = new HostnameVerifier() {
    public boolean verify(String hostname, SSLSession session) {
        return true;
    }
};
```

## Network Libraries and WebViews

```java
OkHttpClient client = new OkHttpClient.Builder()
    .certificatePinner(new CertificatePinner.Builder()
        .add("example.com", "sha256/UwQAapahrjCOjYI3oLUx5AQxPBR02Jz6/E2pt0IeLXA=")
        .build())
    .build();
```

Some applications will implement SSL Pinning, which prevents the application from accepting your intercepting certificate as a valid certificate. This means that you will not be able to monitor the traffic between the application and the server.

For most applications, certificate pinning can be bypassed within seconds, but only if the app uses the API functions that are covered by these tools. If the app is implementing SSL Pinning with a custom framework or library, the SSL Pinning must be manually patched and deactivated, which can be time-consuming.
## OBJECTION

```bash
android sslpinning disable
```

## REFLUTTER

https://github.com/ptswarm/reFlutter

- [ ] Check
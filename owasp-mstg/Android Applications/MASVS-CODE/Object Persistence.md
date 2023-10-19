#MASVS-CODE-4 

1. Make sure that sensitive data has been encrypted and HMACed/signed after serialization/persistence. Evaluate the signature or HMAC before you use the data.
2. Make sure that the keys used in step 1 can't be extracted easily. The user and/or application instance should be properly authenticated/authorized to obtain the keys.
3. Make sure that the data within the de-serialized object is carefully validated before it is actively used.

- [ ] Check
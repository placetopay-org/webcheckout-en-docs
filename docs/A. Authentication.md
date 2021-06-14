# Authentication

The WebCheckout Placetopay API uses Web Services Security UsernameToken Profile 1.1 to authenticate all requests.


Service authentication must be sent on the `auth` object, which must contain the following attributes:

Values like `login` and `secretKey` are provided by Placetopay.
The `nonce` value is random for each request

Value | Description
---------|----------
 **login** | Site identifier.
 **tranKey** | Value resulting from the following operation: `Base64(SHA-1(nonce + seed + secretkey))`.(The nonce in the operation is the original one, that is, the one not included in Base64.)
 **nonce** | Random value for each request coded in Base64.
 **seed** | Current date, which is generated in ISO 8601 format.

 
```json
IMPORTANT NOTICE:

Your API keys hold many privileges, so make sure to keep them secure. Do not share your secret API keys in public repositories like GitHub, client-side codes, etc.
```

## Possible Errors


Code | Cause 
---------|----------
 100 | UsernameToken not provided (Malformed authorization header).
 101 | Site identifier does not exist (Incorrect login or environment not found). 
 102 | 	The TranKey hash does not match (Incorrect or malformed TranKey).
 103 | Seed date over five minutes.
 104 | Inactive site.
 105| Expired site.
 106 | Expired credentials.
 107| Bad definition for UsernameToken (does not comply with WSSE header).
 200| Skip SOAP authentication header.
 10001| Contact Support.

## Frequent Errors

- #### **"Malformed Authentication" Error Message**

This message comes up when the system does not detect a login, tranKey, seed, or nonce included in the auth structure sent. It can also come up if these data are sent but incorrectly, that is, with no application/json content-type parameter so that the server can interpret the request as text instead of as a data array.You can validate this by making the request to the https://dnetix.co/p2p/client  URL and capturing the response. It is a type of mirror request that will allow you to verify the parameters and the message body .

- #### **Error connecting to the service with message ERROR: javax.net.ssl.SSLHandshakeException: Remote host closed connection during handshake**

Due to PCI standards, your servers need TLSv1.2 to receive the request.Please, review the encryption and protocol used to connect to the server. If you use Java, be aware that only versions after version 8 have full support.

- #### **SoapFault responds with the message "Authentication Failed 103"**

EIn the authentication process, Placetopay reviews the Created field; this filed should be in GMT time or local time. If you get this response, it is because your time is not accurate with respect to the real time.We only allow a 5-minute difference between times. You may use NTP to keep your clock's accuracy.

- #### **Although I am giving the EXACT values as those in previous examples to BASE64(SHA1($Nonce + $Created + $tranKey)), I am getting a different password digest.**

Keep in mind that BASE64 should be for the SHA1 raw output, and according to all programming languages, it may be required to configure this option, for example: In PHP base64_encode(sha1( … , true)), this parameter would return the raw output for the SHA1 algorithm.


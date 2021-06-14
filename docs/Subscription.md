---
tags: [Crear sesión]
---

# Subscription

Subscription allows you to save a user's payment method securely (via tokenizing) so they can be subsequently used for collections.

### **Requesting Subscription:**

To use this function, it is necessary to send the subscription structure in the  `RedirectRequest`.

**Ejemplo:**
```json
{
   "auth": {
    "login": "usuarioprueba",
    "tranKey": "jsHJzM3+XG754wXh+aBvi70D9/4=",
    "nonce": "TTJSa05UVmtNR000TlRrM1pqQTRNV1EREprWkRVMU9EZz0=",
    "seed": "2019-04-25T18:17:23-04:00"
    },
    "subscription": { //At this point, we establish that the type of operation is a subscription.
        "reference": "3110",
        "description": "Test subscription"
    },
    "expiration": "2021-04-30T00:00:00-05:00",
    "returnUrl": "https://mysite.com/response/3210",
    "ipAddress": "127.0.0.1",
    "userAgent": "PlacetoPay Sandbox"
}
```


### **Collecting Using a Token**
The response structure contains all the information of the original request and a `subscription` structure with an `instrument` represented in token form.

#### **Considerations:**

 - We recommend making a charge for a minimal amount to make sure that the card is active.
 - The token information should be saved in your site and linked to the user and/or product. After having the token, you may collect on the tokenized payment method using the collect service.
---
tags: [Crear sesión]
internal: true
---

# Payment Methods

When creating a session, you can limit the payment methods. This way, you force your users to make payment in that session with specific payment methods.You can send the list of payment methods in the `paymentMethod` attribute.

**Possible Values:**

Value | Description 
---------|----------
 `visa` |   VISA  cards
 `master` |   MASTERCARD cards
 `amex` |   AMERICAN EXPRESS cards
 `diners` |   DINERS cards
 `discover` |   DISCOVER cards
 `visa_electron` |  debito VISA ELECTRON debit cards
 `ATHMV` | ATH Móvil (only applicable in Puerto Rico)
  `EBATH` | ATH debit (only applicable in Puerto Rico)
 `pse` | PSE (only applicable in Colombia) | 
  

```json
    "payment": {
        "reference": "TEST_20210503_170757",
        "description": "Ipsam eum qui quae animi ut expedita amet.",
        "amount": {
            "currency": "COP",
            "total": 193000
        }
    },
    "expiration": "2021-05-04T17:07:57-05:00",
    "ipAddress": "181.53.226.56",
    "returnUrl": "https://dnetix.co/p2p/client",
    "userAgent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.93 Safari/537.36",
    "paymentMethod": "visa, master, amex"// The payment methods to be used are defined.

```





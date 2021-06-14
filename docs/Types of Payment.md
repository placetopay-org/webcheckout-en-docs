---
tags: [Crear sesión]
---
## Payment 

A payment refers to the process executed after the user enters the information requested in WebCheckout Placetopay and requests the network to collect.

## Mixed Payment

Mixed payments allow you to use several payment methods (enabled for the API key) when paying in a single session.

To use this function, it is necessary to send the attribute `allowPartial` as `TRUE` in the Payment structure.

Example:

```json
{
  "auth": {
    "login": "usuarioprueba",
    "tranKey": "jsHJzM3+XG754wXh+aBvi70D9/4=",
    "nonce": "TTJSa05UVmtNR000TlRrM1pqQTRNV1EREprWkRVMU9EZz0=",
    "seed": "2019-04-25T18:17:23-04:00"
  },

   "payment": {
        "reference": "3210",
        "description": "Test mixed payment",
        "amount": {
            "currency": "COP",
            "total": "10000"
        },
        "allowPartial": true //We establish that the operation will allow mixed payments
    },

    "expiration": "2021-04-30T00:00:00-05:00",
    "returnUrl": "https://mysite.com/response/3210",
    "ipAddress": "127.0.0.1",
    "userAgent": "PlacetoPay Sandbox"
}
```

Additional statuses in a mixed payment session

When obtaining the operation's results, you should be mindful of the following two statuses:

- **APPROVED_PARTIAL:** Means that at least one approved payment is being made, but the session payment has not been made in full.
- **PARTIAL_EXPIRED:** Means that at least one approved payment is being made, but the session payment was not made in full, and the session expired.

It is important to keep the site's business rules in mind when obtaining any one of these two statuses.


## Recurring Payment

It is a recurring charge made by Placetopay for the same amount and at a specific interval (daily, monthly, yearly), per the instruction given in the request.

To use of this function, in the recurring Payment structure, you need to send the required information for said structure in the `recurring` object.

```json
{
  "auth": {
    "login": "usuarioprueba",
    "tranKey": "jsHJzM3+XG754wXh+aBvi70D9/4=",
    "nonce": "TTJSa05UVmtNR000TlRrM1pqQTRNV1EREprWkRVMU9EZz0=",
    "seed": "2019-04-25T18:17:23-04:00"
    },
    "payment": {
        "reference": "3210",
       "description": "Test recurring payment," 
        "amount": {
            "currency": "COP",
            "total": "10000"
        },
        "recurring": { //We establish the characteristics of the recurrence.
            "periodicity": "M",
            "interval": "1",
            "nextPayment": "2019-04-04",
            "maxPeriods": "12"
        }
    },
    "expiration": "2019-03-05T00:00:00-05:00",
    "returnUrl": "https://mysite.com/response/3210",
    "ipAddress": "127.0.0.1",
    "userAgent": "PlacetoPay Sandbox"
}
```


Attribute | Type | Description | Required?
---------|----------|--------- |---------
 **periodicity**  | `string` | Invoice frequency D=Day, M=Month, Y=Year| Required |
 **interval**   | `int` | Interval associated to frequency.| Required |
 **nextPayment**   | `date` |Date of next payment.| Required |
 **maxPeriods**   | `int` | Maximum period number (-1 if there is no restriction)| Required |
 **dueDate**   | `date` |Date to complete payment.| Optional |
 **notificationUrl**   | `string` |URL where the service will notify every time a recurring payment is made.| Optional |


Recurring charges will only be made if the initial transaction is approved.

If a recurring charge fails, reattempts will be made every day for three (3) days; if after said period, the approved transaction is not obtained, the recurrence is cancelled for the cardholder.
 
Recurrence reattempts will stop if it is understood from the first response that there is no sense in reattempting (invalid or stolen card, etc.); that is, reattempts will only be made for the outstanding balances.

Recurrences may only be cancelled in the Placetopay administrative dashboard.
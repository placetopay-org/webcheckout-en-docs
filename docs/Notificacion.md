# Notification

A notification allows the merchant to be informed about the status of the sessions.

Configure a notification URL on your server using ports 80 or 443 and in case the session is canceled or approved, receive a notification via POST.


```json json_schema
{
  "type": "object",
  "properties": {
    "requestID": {
      "type": "integer"
    },
    "reference": {
      "type": "string"
    },
    "signature": {
      "type": "string"
    }
  }
}
```

Asynchronously, a notification of the request status will be sent to a URL defined by the merchant's configuration in PlacetoPay.

**Upon receiving the notification, your site must: **

**Identify operation:** The session identifier requestId and the reference “reference” identify the notified session. For this session, you must validate that the reported operation statuses are pending on your system.

**Validate the authenticity of the notification:** You can validate that it is a response from PlacetoPay by doing a SHA-1 with the data requestId + status + date + secretKey.

**Validate that the transaction is unresolved:**

If you want to get more information about the session you must use the getRequestInformation method.

```json
Under no circumstances reveal your SecretKey anywhere accessible to customers or users of your application.
```

After getting the session status, you can proceed to your site's business rule. (example: if the operation is approved, send an email to the user). 

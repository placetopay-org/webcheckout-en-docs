---
internal: true
---

# Integration Flow

1. To redirect your user to the WebCheckout system, you must use the **`createRequest`** method. If you do not wish to redirect the user, you can use the lightbox option. If the request is processed correctly, the service creates and returns the following in its response:  `requestID` identifier and `processUrl` processing URL.
2. Create a record in your system, link that record to the `requestID`, and leave the status on pending.
3. Redirect the user to the processUrl.
4. The user will complete the payment or registration process in the WebCheckout interface, where they must enter the information to process the payment.
5. Subsequently, the user must select payment method with which they will make the purchase by entering the payment method information.
6. Once the user has completed the process and clicks on ***“Return to merchant”***, they will be directed to the returnUrl return URL (specified attribute when creating the operation).
7.	When you get to your site, use the record `requestID` to submit a query to Placetopay about the session status, using the `getRequestInformation` method.
8.	Execute your business rule based on the status obtained to update it in your database.
9.	Placetopay asynchronously notifies the final session status to your site.
10.	We recommend implementing a probe process to solve any transactions that were left unresolved in steps number 7 and 9.


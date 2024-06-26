---
internal: true
---

# Test you integration

## URL's Base
PlacetoPay enables different base URLs according to the country you are integrating with.


## Tests

Colombia, Costa Rica, Panama, Puerto Rico: https://test.placetopay.com/redirection

Ecuador:https://test.placetopay.ec/redirection

## Production
Colombia, Costa Rica, Panama, Puerto Rico: https://checkout.placetopay.com

Ecuador: https://checkout.placetopay.ec

## Test cards
The cards presented below can be used in PlacetoPay testing environment to simulate the different responses in the integration.

franchise | Credit card number| CVV | expiration date | Behaviour 
-----------|-------------------|-----|---------------------|--------------
Visa | 4005580000000040 | Any (3 digits)| Any future date| Rejected
Visa|	4007000000027| Any (3 digits) | Any future date |	approved
Visa|	4111111111111111| Any (3 digits)| Any future date |	approved
Visa|	4212121212121214| Any (3 digits)| Any future date |	Leave the pending operation as capture mode, the operation must be authorized or canceled in PlacetoPay panel, or otherwise by VOID or SETTLE operations.
Visa|	4666666666666669| Any (3 digits) | Any future date |	This takes 5 minutes to authorize. The idea is to simulate a waiting time in your authorization. So the consumer service will fail over time, forcing the use of Webservice to verify when the operation completes its process. Take into account the consumption times of Webservice.
Visa| 4509564638437551 | Any (3 digits) | Any future date| It leaves the operation pending but when it is consulted it changes to approved.
Visa| 4931974429847108 | Any (3 digits) | Any future date| It leaves the Pending operation but when it is queried it remains pending.
Visa| 4864921336824366 | Any (3 digits) | Any future date| It leaves the Pending operation but when it is queried it changes to rejected.
Diners|	36545407032780| Any (3 digits)| Any future date|	Leave the operation in Manual mode (it must be approved or rejected from the console).
MasterCard|	5424000000000015| Any (3 digits) | Any future date|	approved
MasterCard Credencial (BCO)|	540625 10 00 00 00 08 | Any (3 digits) | Any future date|	approved
AmericanExpress|	370000000000002| Any (4 digits)| Any future date|	approved
Diners|	36018623456787 | Any (3 digits)| Any future date|	approved
BBVA Club Campestre|	8130010000000000 | N/A | N/A |	approved
Visa Electron (Debit card)|	4027390000000006 | Any (3 digits)| Any future date|	approved
Visa Electron (Debit card)|	4215440000000001 | Any (3 digits) | Any future date |	Rejected
Codensa	|5907120000000009 | Any (3 digits) | Any future date|	Rejected
Tarjeta RIS	| 6372000000000007 | N/A | N/A |	Rejected
ATH (Puerto Rico Only)| 0215020177972730  | Any (3 digits) | Any future date| approved.
ATH (Puerto Rico Only)| 2215714777972730  | Any (3 digits) | Any future date| approved.
ATH (Puerto Rico Only)| 2215716999194052  | Any (3 digits) | Any future date| It leaves the operation pending but when it is consulted it changes to approved.
ATH (Puerto Rico Only)| 0215025888083941  | Any (3 digits) | Any future date| It leaves the Pending operation but when it is queried it remains pending.
ATH (Puerto Rico Only)| 0215027111105163  | Any (3 digits) | Any future date| It leaves the Pending operation but when it is queried it changes to rejected.
ATH (Puerto Rico Only)| 0215026116775785  | Any (3 digits) | Any future date| Rejected.
ATH (Puerto Rico Only)| 2215719446775653  | Any (3 digits) | Any future date| Rejected.
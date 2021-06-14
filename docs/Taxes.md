---
tags: [Crear sesión]
---

# Taxes

The types of tax are the different kinds of taxes people are required to pay to an entity.

In this sense, a type of tax is applied, depending on the activity. This is based on the regulations for each tax system.

In WebCheckout Placetopay, taxes are sent in the  `amount` object that is used in the  `taxes` structure.

            "taxes": [
                {
                    "kind": "ice",
                    "amount": 6.84
                },
                {
                    "kind": "valueAddedTax",
                    "amount": 10.83
                }
            ],

The  `kind`  value represents the type of tax that is included in the payment. The different kinds of taxes are:


Kind | Country
---------|----------
 **valueAddedTax** | All
 **exciseDuty** | All
 **ice** | All
 **airportTax** | Colombia y Ecuador
 **stateTax** | Puerto Rico
 **MunicipalTax** | Puerto Rico 
**reducedStateTax** | Puerto Rico
 
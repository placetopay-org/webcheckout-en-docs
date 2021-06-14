---
tags: [Crear sesión]
---


# Types of Documents

When creating a session, if you use one of the  `payer`, `buyer`, or `shipping` structures, you should use the  DocumentType attribute to send the following codes, depending on the country:

```json
IMPORTANT NOTICE:

Depending on the type of document sent, the system will perform the validation based on regular expressions.
```


### Global


Code| Type of Document| Validation Rule
---------|----------|----------
 PPN	 | Passport | `'/^[a-zA-Z0-9_]{4,16}$/'`
 TAX | TAX | `'/^[a-zA-Z0-9_]{4,16}$/'`
 LIC | Labeler Identification Code | `'/^[a-zA-Z0-9_]{4,16}$/'`

### Puerto Rico (PR)

For integrations in this country, neither the `DocumentType` nor the` Document` is sent


### Colombia (CO)

Code| Type of Document | Validation Rule
---------|---------- |----------
 CC | Cédula de ciudadanía  | `'/^[1-9][0-9]{3,9}$/'`
 CE | Cédula de extranjería | `'/^([a-zA-Z]{1,5})?[1-9][0-9]{3,7}$/'`
 TI | Tarjeta de identidad| `'/^[1-9][0-9]{4,11}$/'`
 NIT | Número de Identificación Tributaria|` '/^[1-9]\d{6,9}$/'`
 RUT | Registro único tributario| `'/^[1-9]\d{6,9}$/'`
 
### Ecuador (EC)
Code| Type of Document| Validation Rule
---------|----------|---------
 CI | Cédula de identidad|`'/^\d{10}$/'`
 RUC | Registro Único de Contribuyentes|`'/^\d{13}$/'`
 

### Costa Rica (CR)

Code| Type of Document| Validation Rule
---------|----------|------------
 CRCPF | Cédula personal física |`'/^[1-9][0-9]{8}$/'`
 CPJ | Cédula personal juridica |`'/^[1-9][0-9]{9}$/'`
 DIMEX | DIMEX- Docuemnto de identificación de Migración y Extranjería|`'/^[1-9][0-9]{10,11}$/'`
  DIDI | DIDI - Docuemnto de identificación de diplomáticos|`'/^[1-9][0-9]{10,11}$/'`

### Chile (CL)

Code| Type of Document| Validation Rule
---------|----------|------------
 CLRUT | Cédula personal física |`'/^(\d{1,2}(?:\.?\d{1,3}){2}-[\dkK])$/'`


### Panamá (PA)

Code| Type of Document| Validation Rule
---------|----------|------------
 CIP | Cédula de identidad personal| `/^(N,E,PE\d+)?\d{2,6}\d{2,6}$/`

 ### Brasil (BR)

 Code| Type of Document| Validation Rule
---------|----------|------------
 CPF | Cadastro de Pessoas Físicas|`'/^\d{10,11}$/'`


 ### Perú (PE)

  Code| Type of Document| Validation Rule
---------|----------|------------
 DNI | DNI|`'/^\d{8}$/'`




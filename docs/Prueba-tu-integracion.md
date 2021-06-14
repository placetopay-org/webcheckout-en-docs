# Prueba tu integracion

## URL's Base
Placetopay habilita diferentes URL base según el pais con el que te estas integrando

### Pruebas
- Colombia, Costa Rica, Panama, Puerto Rico:
- Ecuador:

### Producción
- Colombia, Costa Rica, Panama, Puerto Rico:
- Ecuador:



## Tarjetas de prueba

Las de tarjetas presentadas a continuación pueden ser usadas en el ambiente de pruebas de Placetopay para simular las diferentes respuestas en la integración

Franquicia | Número de tarjeta | CVV | Fecha de expiración | Comportamiento 
-----------|-------------------|-----|---------------------|--------------
Visa | 4005580000000040 | Cualquiera (3 digitos) | Cualquier fecha futura | Rechaza
Visa|	4007000000027| Cualquiera (3 digitos) | Cualquier fecha futura |	Aprueba
Visa|	4111111111111111| Cualquiera (3 digitos) | Cualquier fecha futura |	Aprueba
Visa|	4212121212121214| Cualquiera (3 digitos) | Cualquier fecha futura |	Deja la operación pendiente como modo de captura, la operación debe ser autorizada o cancelada en el panel de Place to Pay o de otra manera por operaciones de VOID o SETTLE.
Visa|	4666666666666669| Cualquiera (3 digitos) | Cualquier fecha futura |	Este toma 5 minutos para autorizar. La idea es simular un tiempo de espera en su autorización. Así que el servicio de consumo fallará por el tiempo, lo que obligará al uso del Webservice para verificar cuando la operación completa su proceso. Tenga en cuenta los tiempos de consumo de Webservice.
Diners|	36545407032780| Cualquiera (3 digitos) | Cualquier fecha futura |	Deja la operación en estado Manual (se debe aprobar o rechazar desde la consola)
MasterCard|	5424000000000015| Cualquiera (3 digitos) | Cualquier fecha futura |	Aprueba
MasterCard Credencial (BCO)|	540625 10 00 00 00 08 | Cualquiera (3 digitos) | Cualquier fecha futura |	Aprueba
AmericanExpress|	370000000000002| Cualquiera (4 digitos) | Cualquier fecha futura |	Aprueba
Diners|	36018623456787 | Cualquiera (3 digitos) | Cualquier fecha futura |	Aprueba
BBVA Club Campestre|	8130010000000000 | N/A | N/A |	Aprueba
Visa Electron (Debit card)|	4027390000000006 | Cualquiera (3 digitos) | Cualquier fecha futura |	Aprueba
Visa Electron (Debit card)|	4215440000000001 | Cualquiera (3 digitos) | Cualquier fecha futura |	Rechaza
Codensa	|5907120000000009 | Cualquiera (3 digitos) | Cualquier fecha futura |	Rechaza
Tarjeta RIS	| 6372000000000007 | N/A | N/A |	Rechaza


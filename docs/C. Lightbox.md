---
internal: true
---


# Lightbox

Avoid redirecting your user by using a Lightbox window, which will take up the entire screen with a clear background  and the WebCheckout Placetopay page is shown at the center, inside a dynamically resizable box.

Steps to use the lightbox:

1.	Use your country URL.

**Note:** The country URL is formed by `URL_Base`/lightbox.min.js

	
2.	Upload the JavaScript label in your page using your country's origin in the src attribute `<script src="REPLACE_WITH_YOUR_COUNTRY_URL"></script>.`
3.	Configure the response callback so that it performs the action you need; in this case, we only show the information in the bottom field.
```json
	P.on('response', function(data) {
	    $("#lightbox-response").html(JSON.stringify(data, null, 2));
	});
```
4.	Obtain the Placetopay `processURL` .
5.	Initialize the URL in the lightbox; in this example, it is loaded in the `processUrl` variable.
```json
P.init(processUrl);
```
** Note: ** If you wish to change the iframe background transparency, you can send it as a parameter when initializing, as follows: it should be a value between 0 and 1, where 1 is not transparent at all, and 0 is completely transparent.
```json
P.init(processUrl, { opacity: 0.4 });
```
**IMPORTANT NOTICE** 

Keep in mind that if the lightbox does not find a suitable environment to perform (poor JS support, previous or old browser version), it will execute a redirection to the processing URL.


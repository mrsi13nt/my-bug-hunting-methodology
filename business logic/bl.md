# Business logic

### 1- Excessive trust in client-side controls

Fundamentally the developers take the fact into account that users will directly interact with the application in the desired way, ignoring the fact that any malicious input from the client side can adversely affect the web application. Attackers mostly use the Burp proxy to tamper with the data after it has been passed through the browser to fail any kind of client-side validation mechanism used by the developers.

Let’s understand it with an example-

Supposedly a user planned to buy Jeans from a very famous e-commerce website, which has a price tag of ‘X’. Now after adding it to the cart, he/she further send the request to the proxy server instead of to the server and tries to tamper with the price, via the ‘POST /cart’ request. By simply passing the arbitrary value to the price parameter and then forwarding it to the server, the original price will be modified to the new value supplied by the end-user, hence compromising the integrity as well as the functionality of the web application.

* [example (Excessive trust in client-side controls)](https://portswigger.net/web-security/logic-flaws/examples/lab-logic-flaws-excessive-trust-in-client-side-controls)


### 2- BYPASSING THE TWO-FACTOR AUTHENTICATION

Many web-application enhance their security by implementing 2 Factor authentication to prevent the unintended user from login. However, the improper implementation of 2FA can result in a complete bypass of the login panel.

Many websites that use 2FA require the user to log in on one page before entering the security code on the other. But assuming that user will interact in the same way is harmful because an attacker can use the previously discussed tool Burp Proxy and repeater to bypass the login page, once the attacker understands the workflow of the application, such as how the application is maintaining and identifying the user session, it would just matter of time before the attacker gain access to several accounts.

[example (2FA simple bypass)](https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-simple-bypass)

[example 2 (2FA broken logic)](https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-broken-logic)
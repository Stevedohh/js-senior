# CSP
**Content Security Policy (CSP)** is an added layer of security that helps to detect and mitigate certain types of attacks, including **Cross-Site Scripting (XSS)** and data injection attacks. 

CSP provides a standard method for website owners to declare approved origins of content that browsers should be allowed to load on that website

**Examples**

```ad-example
A web site administrator wants all content to come from the site's own origin (this excludes subdomains.)

`Content-Security-Policy: default-src 'self'`
```

```ad-example
A web site administrator wants to allow content from a trusted domain and all its subdomains (it doesn't have to be the same domain that the CSP is set on.)

`Content-Security-Policy: default-src 'self' example.com *.example.com`

```

```ad-example

A web site administrator wants to allow users of a web application to include images from any origin in their own content, but to restrict audio or video media to trusted providers, and all scripts only to a specific server that hosts trusted code.

`Content-Security-Policy: default-src 'self'; img-src *; media-src example.org example.net; script-src userscripts.example.com`

```

# XSS

Cross-site scripting (XSS) is a security exploit which allows an attacker to inject into a website malicious client-side code. This code is executed by the victims and lets the attackers bypass access controls and impersonate users.

**Example of XSS**

![[Pasted image 20221014195601.png]]

# Click-jacking

**Clickjacking** is the practice of tricking a user into clicking on a link, button, etc. that is other than what the user thinks it is. This can be used, for example, to steal login credentials or to get the user's unwitting permission to install a piece of malware.

# CSRF 

**CSRF (sometimes also called XSRF)** The attacker causes the user's browser to perform a request to the website's backend without the user's consent or knowledge. An attacker can use an XSS payload to launch a CSRF attack.

**Example**

In this situation, someone includes an image that isn't really an image, instead it really is a request to your bank's server to withdraw money:

```ad-example
`<img
src="https://bank.example.com/withdraw&account=bob&amount=10000&for=mallory" />`

```

Now, if you are logged into your bank account and your cookies are still valid (and there is no other validation), you will transfer money as soon as you load the HTML that contains this image. For endpoints that require a POST request, it's possible to programmatically trigger a **form** submit (perhaps in an invisible **iframe**) when the page is loaded

```HTML
<form action="https://bank.example.com/withdraw" method="POST">
  <input type="hidden" name="account" value="bob" />
  <input type="hidden" name="amount" value="1000000" />
  <input type="hidden" name="for" value="mallory" />
</form>

<script>
  window.addEventListener('DOMContentLoaded', (e) => { document.querySelector('form').submit(); }
</script>
```

## How to prevent

-   GET endpoints should be idempotent. Also POST endpoints should not interchangeably accept GET requests with parameters in the query string.
-   A CSRF token should be included in **form** elements via a hidden input field. This token should be unique per user and stored (for example, in a cookie) such that the server can look up the expected value when the request is sent. For all non-GET requests that have the potential to perform an action, this input field should be compared against the expected value. If there is a mismatch, the request should be aborted.
-   The token should be regenerated on sign-in.

```js
@TODO Расписать типы токенов
``` 

# Man-in-the-middle (MitM)

A third party guy intercepts traffic between a web server and a client (browser), and impersonates the web server in order to capture data (such as login credentials or credit card information). The traffic is passed through, possibly with alterations. 

```ad-info
Open Wi-Fi networks are a typically means of executing this attack.
```

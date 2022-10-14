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

Example of XSS


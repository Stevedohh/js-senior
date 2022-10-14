
# Same-Origin Policy (SOP)

Same-origin policy means that a request can only be made from one URL to another if the receiver and the sender have the same protocol, host, and port. Browsers use same-origin policy (SOP) to prevent cross-site scripting attacks.

```ad-warning
Images and iframes works because in SOP we have exceptions. We can load iframe but we could not read it.
```

## Cross-origin network access

The same-origin policy controls interactions between two different origins, such as when you use [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) or an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element. These interactions are typically placed into three categories:

-   Cross-origin _writes_ are typically allowed. Examples are links, redirects, and form submissions. Some HTTP requests require [preflight](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS#preflighted_requests).
-   Cross-origin _embedding_ is typically allowed. (Examples are listed below.)

Here are some examples of resources which may be embedded cross-origin:

-   JavaScript with `<script src="…"></script>`. Error details for syntax errors are only available for same-origin scripts.
-   CSS applied with `<link rel="stylesheet" href="…">`. Due to the relaxed syntax rules of CSS, cross-origin CSS requires a correct `Content-Type` header.
-   Images displayed by `<img>`
-   Media played by `<video>` and `<audio>`.
-   External resources embedded with `<object>` and `<embed>`
-   Fonts applied with `@font-face` Some browsers allow cross-origin fonts, others require same-origin.
-   Anything embedded by `<iframe>`. Sites can use the `X-Frame-Options` header to prevent cross-origin framing.

# CORS

**Cross-Origin Resource Sharing (CORS)** is an HTTP-header based mechanism that allows a server to indicate any origins (domain, scheme, or port) other than its own from which a browser should permit loading resources. CORS also relies on a mechanism by which browsers make a **"preflight"** request to the server hosting the cross-origin resource, in order to check that the server will permit the actual request. In that preflight, the browser sends headers that indicate the HTTP method and headers that will be used in the actual request.


## Functional overview

The Cross-Origin Resource Sharing standard works by adding new HTTP headers that let servers describe which origins are permitted to read that information from a web browser. Additionally, for HTTP request methods that can cause side-effects on server data (in particular, HTTP methods other than GET, or POST with certain MIME types), the specification mandates that browsers "preflight" the request, soliciting supported methods from the server with the HTTP OPTIONS request method, and then, upon "approval" from the server, sending the actual request. Servers can also inform clients whether "credentials" (such as Cookies and HTTP Authentication) should be sent with requests.
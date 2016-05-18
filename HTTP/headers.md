Headers about proxy
---
* X-Forwarded-For
* X-Forwarded-Proto

Headers about Security
---
* X-Xss-Protection
>This filter is built into most recent web browsers (IE 8+, Chrome 4+), and is usually enabled by default. Although it is not designed as first and only defence against Cross-Site Scripting, it acts as an additional layer of protection. "X-XSS-Protection" header with value "1" (i.e. Enabled)
ref: [Apache](http://httpd.apache.org/docs/2.2/mod/mod_headers.html),  [IIS](https://technet.microsoft.com/pl-pl/library/cc753133%28v=ws.10%29.aspx),  [Nginx](http://nginx.org/en/docs/http/ngx_http_headers_module.html)

* X-Content-Type-Options
>This action may prevent untrusted content (e.g. user uploaded content) from being executed on the user browser (after a malicious naming, for example).  "X-Content-Type-Options" header with value "nosniff", and mime type should be following type: "application/ecmascript", "application/javascript", "application/x-javascript", "text/ecmascript", "text/javascript", "text/jscript", "text/x-javascript", "text/vbs", "text/vbscript"
ref: [Apache](http://httpd.apache.org/docs/2.2/mod/mod_headers.html),  [IIS](https://technet.microsoft.com/pl-pl/library/cc753133%28v=ws.10%29.aspx),  [Nginx](http://nginx.org/en/docs/http/ngx_http_headers_module.html)

* Content-Security-Policy
>The "Content-Security-Policy" header is designed to modify the way browsers render pages, and thus to protect from various cross-site injections, including Cross-Site Scripting. ref: [Apache](http://httpd.apache.org/docs/2.2/mod/mod_headers.html),  [IIS](https://technet.microsoft.com/pl-pl/library/cc753133%28v=ws.10%29.aspx),  [Nginx](http://nginx.org/en/docs/http/ngx_http_headers_module.html)


* Strict-Transport-Security
>HTTP Strict Transport Security (HSTS) is a web security policy mechanism whereby a web server declares that complying user agents (such as a web browser) are to interact with it using only secure HTTP (HTTPS) connections.
The HSTS Policy is communicated by the server to the user agent via a HTTP response header field named "Strict-Transport-Security". HSTS Policy specifies a period of time during which the user agent shall access the server in only secure fashion.
ref: [Wiki](http://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security), [Apache](http://linux-audit.com/configure-hsts-http-strict-transport-security-apache-nginx/),  [IIS](http://www.hanselman.com/blog/HowToEnableHTTPStrictTransportSecurityHSTSInIIS7.aspx),  [Nginx](https://www.nginx.com/blog/http-strict-transport-security-hsts-and-nginx/)

## Security Recommendations
We recommend the following for deployed versions of any and all SafePlace APIs:

- The following headers (and appropriate values) should be returned from the server to client:
	- X-Frame-Options
	- X-XSS-Protection
	- X-Content-Type-Options
	- Expect-CT
	- Feature-Policy
	- Strict-Transport-Security
- A suitable "Referrer-Policy" header is included, such as "no-referrer" or "same-origin"
- The server running SafePlaces should not expose any information about itself that is unneeded (i.e., type of server (nginx) and version (1.17.8))
- Implement an appropriate security policy
- All SafePlaces APIs should be deployed behind an appropriately configured firewall
- All requests to and from a SafePlaces API should be over HTTPS
- Old versions of SSL and TLS protocols, algorithms, ciphers, and configuration are disabled, such as SSLv2, SSLv3, or TLS 1.0 and TLS 1.1. The latest version of TLS should be the preferred cipher suite.
- The web server should be configured under a low-privilege system user account.
-  Any debug model provided by the web or application server is disabled.

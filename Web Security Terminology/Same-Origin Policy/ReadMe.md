# Same-Origin Policy

Web security is something that the general public understands exist but doesn’t really know how it works. Below we will try to examine some of the first steps of Same-Origin Policy.

[Same-Origin Policy](https://developer.mozilla.org/en-US/docs/Glossary/Same-origin_policy) is a critical safety feature that restricts document interaction with different origin resources. What this means is that a server can restrict access to it’s data if the browser sends a request from a different origin than the server. This begs the question what is an “origin”? Also, how are origins compared?

Origin is a portion of the url consisting of a specific protocol(scheme), host, and port. Schemes are the Hyper Text Transfer Protocols (“http://” & “https://”). The host is the website (www.example.com or example.com). The port is a number code at the end of the host (ftp 21, qotd 17, or WWW 80). When no port is specified, the browser defaults to port 80. The endpoints (ex./index.html/messages )are not part of the origin.



# Same-Origin Policy

Web security is something that the general public understands exist but doesn’t really know how it works. Below we will try to examine some of the first steps of Same-Origin Policy and CORS.

![img](https://github.com/paulveillard/cybersecurity-web-security/blob/main/Web%20Security%20Terminology/Same-Origin%20Policy/img/sop-1.jpg)

[Same-Origin Policy](https://developer.mozilla.org/en-US/docs/Glossary/Same-origin_policy) is a critical safety feature that restricts document interaction with different origin resources. What this means is that a server can restrict access to it’s data if the browser sends a request from a different origin than the server. This begs the question what is an “origin”? Also, how are origins compared?

Origin is a portion of the url consisting of a specific protocol(scheme), host, and port.

![image1](https://github.com/paulveillard/cybersecurity-web-security/blob/main/Web%20Security%20Terminology/Same-Origin%20Policy/img/sop-4.png)

Schemes are the Hyper Text Transfer Protocols (“http://” & “https://”). The host is the website (www.example.com or example.com). The port is a number code at the end of the host (ftp 21, qotd 17, or WWW 80). When no port is specified, the browser defaults to port 80. The endpoints (ex./index.html/messages ) are not part of the origin.


Now if websites could not interact with each other, then the internet would be rather dull. How could any site interact with other sites ?How could google or facebook interact with each other and share data? This is where CORS comes into play.

CORS stands for Cross Origin Reference Sharing. With CORS, browsers have a work-around in order to get data from servers. Websites or servers that use CORS allow cross reference http requests. The way this works is a browser sends a http request (GET, POST, PUT, etc.) with special headers that the server reviews. After the servers review the headers, the server will either accept the request and comply or reject the request and decline. Response headers are typically sent.



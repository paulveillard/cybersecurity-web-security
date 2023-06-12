# Same-Origin Policy

Web security is something that the general public understands exist but doesn’t really know how it works. Below we will try to examine some of the first steps of Same-Origin Policy and CORS.

![img](https://github.com/paulveillard/cybersecurity-web-security/blob/main/Web%20Security%20Terminology/Same-Origin%20Policy/img/sop-1.jpg)

[Same-Origin Policy](https://developer.mozilla.org/en-US/docs/Glossary/Same-origin_policy) is a critical safety feature that restricts document interaction with different origin resources. What this means is that a server can restrict access to it’s data if the browser sends a request from a different origin than the server. This begs the question what is an “origin”? Also, how are origins compared?

Origin is a portion of the url consisting of a specific protocol(scheme), host, and port.

![image1](https://github.com/paulveillard/cybersecurity-web-security/blob/main/Web%20Security%20Terminology/Same-Origin%20Policy/img/sop-4.png)

Schemes are the Hyper Text Transfer Protocols (“http://” & “https://”). The host is the website (www.example.com or example.com). The port is a number code at the end of the host (ftp 21, qotd 17, or WWW 80). When no port is specified, the browser defaults to port 80. The endpoints (ex./index.html/messages ) are not part of the origin.

![image2](https://github.com/paulveillard/cybersecurity-web-security/blob/main/Web%20Security%20Terminology/Same-Origin%20Policy/img/sop-2.PNG)

![image3](https://github.com/paulveillard/cybersecurity-web-security/blob/main/Web%20Security%20Terminology/Same-Origin%20Policy/img/sop-3.PNG)

Now if websites could not interact with each other, then the internet would be rather dull. How could any site interact with other sites ?How could google or facebook interact with each other and share data? This is where CORS comes into play.

CORS stands for Cross Origin Reference Sharing. With CORS, browsers have a work-around in order to get data from servers. Websites or servers that use CORS allow cross reference http requests. The way this works is a browser sends a http request (GET, POST, PUT, etc.) with special headers that the server reviews. After the servers review the headers, the server will either accept the request and comply or reject the request and decline. Response headers are typically sent.


After reviewing the image above, the JavaScript, Browser, and Server are the three key players in the dialogue of an HTTP request. Finally after 300+ words into this blog we see JavaScript. JavaScript is the brains that gets the Browser to make a request to the server. Let me state again, the Browser makes the HTTP request to the Server. JavaScript tells the Browser what to ask for. This is the part where JavaScript code comes into play.

After searching MDN and W3C for Same-Origin Policy and CORS, I kept seeing the use of XMLHttpRequest and Fetch API. I was familiar with using jQuery’s $.ajax to write HTTP requests but I wanted to find out what Fetch was. Was Fetch part of JavaScript? Come to find out that Fetch API is not part of JavaScript, but the Promise fetch() function is. So I used the fetch() function to make a GET request to a server and pull some mock data for better clarification on the CORS topic. See the code below.

```
let users = fetch(‘http://parse.example.com//messages', {
  method: ‘GET’,
  headers: {
  ‘Xample-API-Key’: ‘c1d5b686A159765b1’,
  ‘Xample-Application-Id’: ‘7639d2d2770d83jh85’
 },
}).then(response => {
  console.log(response);
  return response.json();
}).then(data => {
  document.write(‘<title>Fetch Example</title>’, “<h1>Fetch CORS  Example</h1>”,
 data.results.map(user => `<div>
 <h3><i>Name:</i> ${user.username}</h3>
 <p><i>Room:</i> ${user.roomname}</p>
 <a><i>ID:</i> ${user.objectId}</a></div>`));
 return data;
});
console.log(users);
```


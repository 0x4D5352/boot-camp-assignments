    Cybersecurity
Module 12 Challenge Submission File

Web Development

Make a copy of this document to work in, and then respond to each question below the prompt. Save and submit this completed file as your Challenge deliverable.

HTTP Requests and Responses

What type of architecture does the HTTP request and response process occur in?

Client-Server - a request is sent from the client to the server, and the server sends a response back to the client.


What are the parts of an HTTP request?

A Request Line, which specifies the method, the resource identifier, and the protocol version. E.g. GET /index.html HTTP/1.1
Header information, such as Host, User-Agent, and/or Connection - this adds more context to the request that can help the server curate a response that fits with the needs/capacity of the client, or provides the server with information specific to the client for data-gathering purposes.
An empty line - essentially a standalone \n or \n\r (as windows requires a carriage return in addition to a line feed) to let the server know that the header has finished
A request body - optional additional data, such as the content for a POST or PUT request.


Which part of an HTTP request is optional?

As stated: the request body.


What are the three parts of an HTTP response?

A status line - the protocol, the status code, and a related text phrase. E.g HTTP/1.1 200 OK
Header information, much like for the HTTP request. An empty line is required at the end, like in HTTP requests
An optional message body, such as the content for the webpage requested.


Which number class of status codes represents errors?

4xx and 5xx, 4xx for client-side errors and 5xx for server-side errors.


What are the two most common request methods a security professional encounters?

Not sure we covered this in class, but I know one is GET. The other is either going to be OPTIONS to see what possible methods can be chosen, POST to try and push data to the server, or TRACE to enumerate additional information 


Which type of HTTP request method is used to send data?

POST. 


Which part of an HTTP request contains the data being sent to the server?

The request body


In which part of an HTTP response does the browser receive the web code to generate and style a webpage?

The response body


Using curl

 What are the advantages of using curl over the browser?

works in the command line, which means you can automate processes through scripting.
allows for custom header tags, which allows you to present as whatever kind of “browser” you want, which can reduce your footprint when doing recon.
request methods are much easier to access, making enumeration faster.  


Which curl option changes the request method?

-X [METHOD]; e.g. curl -X POST http://website.url/path or curl -X HEAD http://another.site/only.header


 Which curl option sets request headers?

-H “Header-Field: contents”; e.g. curl http://website.url/path -H “User-Agent: Mozilla/5.0” (to pretend we’re viewing with a firefox browser)


 Which curl option is used to view the response header?

--head; e.g curl --head https://website.for/header


Which request method might an attacker use to figure out what HTTP requests an HTTP server will accept?

-X OPTIONS




Sessions and Cookies

 Which response header sends a cookie to the client?

HTTP/1.1 200 OK
Content-type: text/html
Set-Cookie: cart=Bob ← this one!


 Which request header will continue the client's session?

GET /cart HTTP/1.1
Host: www.example.org
Cookie: cart=Bob ← also this one!



Example HTTP Requests and Responses

Use the following sample HTTP request and response to answer the questions in this section:

HTTP Request

POST /login.php HTTP/1.1
Host: example.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 34
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.132 Mobile Safari/537.36

username=Barbara&password=password


 What is the request method?

POST


 Which header expresses the client's preference for an encrypted response?

Upgrade-Insecure-Requests: 1


 Does the request have a user session associated with it?

No, as there is no cookie header attached




 What kind of data is being sent from this request body?

A username and password to login to the website example.com


HTTP Response

HTTP/1.1 200 OK
Date: Mon, 16 Mar 2020 17:05:43 GMT
Last-Modified: Sat, 01 Feb 2020 00:00:00 GMT
Content-Encoding: gzip
Expires: Fri, 01 May 2020 00:00:00 GMT
Server: Apache
Set-Cookie: SessionID=5
Content-Type: text/html; charset=UTF-8
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type: NoSniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block

[page content]


 What is the response status code?

200 OK - the request was successful


 What web server is handling this HTTP response?

Apache


 Does this response have a user session associated with it?

Yes, the Set-Cookie header has the content SessionID=5.


 What kind of content is likely to be in the [page content] response body?

Text (unicode, specifically!)


 If your class covered security headers, what security request headers have been included? NOTE: i referenced the mozilla web docs for this one and some of the descriptions are heavily sourced from there

Strict-Transport-Security, which enforces HTTPS connections.
X-Content-Type, which currently says to block all requests that align with a MIME sniffing attack, where the destination type and the MIME type don’t match up.
X-Frame-Options, which is currently set to prevent any website from trying to load the webpage in an HTML frame, which helps stop click-jacking attacks.
X-XSS-Protection, which is an apparently outdated way to try and prevent cross-site scripting. According to the MDN web docs, the better solution is to have “Content-Security-Policy: ‘unsafe-inline’”.


Monoliths and Microservices

What are the individual components of microservices called?

Service(s)


What is a service that writes to a database and communicates to other services?

API


What type of underlying technology allows for microservices to become scalable and have redundancy?

Cloud Computing


Deploy and Test a Container Set

What tool can you use to deploy multiple containers at once?

Docker Compose


What kind of file format is required to deploy a container set?

.yml, a YAML (YAML Ain’t Markup Language) file.


Databases

Which type of SQL query would you use to view all the information in a table called customers?

SELECT * FROM customers;


Which type of SQL query would you use to enter new data into a table? (You don't need a full query, just the first part of the statement.)

INSERT INTO


 Why would you never run DELETE FROM <table-name>; by itself?

That deletes the entire table, whether you meant to or not.


Bonus Activity: The Cookie Jar

Question 1: Did you see any obvious confirmation of a login? (Y/N)

Yes! In the docker logs, there’s a 302 redirect notice, which on its own doesn’t necessarily mean a success, but in the verbose output of the curl command, there’s two header fields worth noticing:

Set-Cookie: wordpress_logged_in_…… - this cookie likely tells the browser on subsequent attempts to access the page that this account has validated their login recently and doesn’t need to enter their login information again
X-Redirect-By: WordPress && Location: http://localhost:8080/wp-admin


Question 2: How many items exist in this file?

Three Items: wordpress_test_cookie, wordpress, and wordpress_logged_in.


Question 3: Is it obvious that you can access the dashboard? (Y/N)

Yes! On the docker logs, I can see a 200 (OK) response code, and the curl response shows the entire html output of the index.php page. 


Question 4: Look through the output where Dashboard is highlighted. Does any of the wording on this page seem familiar? (Y/N) If so, you should be successfully logged in to your Editor's dashboard.

Yes! I can see “Welcome to your WordPress Dashboard”, as well as a lot of other paragraphs and items relating to the admin dashboard I could see inside of Chrome.


Question 5: What happens this time?

Both the docker logs and the verbose output of curl show that I received a 403 Forbidden response code, showing that I don’t have correct permissions to access the page.





© 2023 edX Boot Camps LLC. Confidential and Proprietary. All Rights Reserved.

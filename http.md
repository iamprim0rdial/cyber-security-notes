# HTTP or HTTP/s

Http is a Application layer protocol. It Stand for Hypertext transfer protocol . It work as mediator between client and server  . it tell how a client (end user) can communicate with server . It uses http request and response system . it is very basic web protocol . **it work on port 80** . It is not secure protocol because every request and response are clearly visible (vulnerable to MITM attack)  anyone can intercept the request and see the request and make changes to overcome this problem new protocol is introduced HTTP/s TLS protocol same as HTTP where s stand for Secure Socket Layer/Transport Layer protocol . It work on port **443** . It provide Secure tunnelling system so that every request it Encrypted 
HTTPs uses SSL to encrypt the data that is transferred between two parties encryption . SSL uses the RSA algorithm . 

# **HTTP Request and Response**
- **Request:** when client send some packet in order to retrieve some information or to access some resource this refer to http request .
- **Response:** when server give back reply of your request is known as response 

---

# HTTP Request Method
When client request something according to their need . It send some packet with different type of methods . These methods are pre-defined and every methods has there own work. 

- **GET**: Retrieve data from the server.
- **POST**: Submit data to be processed by the server.
- **PUT**: Update existing data on the server.
- **HEAD**: Retrieve metadata about a resource (without the body).
- **DELETE**: Remove a resource from the server.
- **OPTIONS**: Request available communication options for a resource.


---

# HTTP Responses
When Server send response of requested resource . Firstly server check ! are you an authorised person ? to access that resource . Acc. to auth. process server send response in 3 digit code . These codes called HTTP Status Code: 

- **1XX - Informational Responses**: These codes indicate that the request was received and is being processed.
  - **100 Continue**: The client can continue with the request (usually after sending the headers).
  - **101 Switching Protocols**: The server is switching protocols, as per the client's request.

- **2XX - Successful Responses**: These codes show that the request was successful.
  - **200 OK**: The request was successful and the server has returned the requested data.
  - **201 Created**: The request was successful, and a resource was created (commonly used with POST).
  - **202 Accepted**: The request has been accepted for processing, but the processing isn't completed.
  - **204 No Content**: The server successfully processed the request, but there is no content to return (e.g., after DELETE request).
  
- **3XX - Redirection Responses**: These codes are used when further action is needed to fulfill the request.
  - **301 Moved Permanently**: The requested resource has been permanently moved to a new location.
  - **302 Found**: The requested resource resides temporarily under a different URL.
  - **303 See Other**: The server is redirecting the client to a different resource.
  - **304 Not Modified**: The resource has not been modified since the last request.
  - **307 Temporary Redirect**: The server is redirecting the client to a different resource temporarily.
  - **308 Permanent Redirect**: The resource has permanently moved, and the client should update the URL.

- **4XX - Client Error Responses**: These indicate errors in the request sent by the client.
  - **400 Bad Request**: The server cannot process the request due to malformed syntax.
  - **401 Unauthorized**: Authentication is required and has failed or has not been provided.
  - **403 Forbidden**: The server understands the request, but the client does not have permission to access the resource.
  - **404 Not Found**: The requested resource could not be found on the server.
  - **405 Method Not Allowed**: The request method is not supported by the resource (e.g., GET on a POST-only resource).
  - **406 Not Acceptable**: The requested resource is only capable of generating content not acceptable according to the `Accept` headers sent in the request.
  - **408 Request Timeout**: The server timed out waiting for the client to send the request.
  - **409 Conflict**: The request could not be completed due to a conflict with the current state of the resource.
  - **410 Gone**: The resource is no longer available and will not be available again.
  - **411 Length Required**: The server refuses to process the request without a `Content-Length` header.
  - **429 Too Many Requests**: The client has sent too many requests in a given amount of time.

- **5XX - Server Error Responses**: These codes indicate problems with the server's ability to process the request.
  - **500 Internal Server Error**: A generic error message indicating that the server encountered an unexpected condition.
  - **501 Not Implemented**: The server does not support the functionality required to fulfill the request.
  - **502 Bad Gateway**: The server received an invalid response from the upstream server it accessed in attempting to fulfill the request.
  - **503 Service Unavailable**: The server is currently unable to handle the request due to temporary overload or maintenance.
  - **504 Gateway Timeout**: The server did not receive a timely response from an upstream server.
  - **505 HTTP Version Not Supported**: The server does not support the HTTP protocol version that was used in the request.

### Some Diff Case
- **418 I'm a teapot**: Defined in RFC 2324 as an April Fools' joke, this code is used by some servers as a humorous error when a teapot refuses to brew coffee.
- **419 Page Expired**: Sometimes used in web applications to signify an expired CSRF token or session timeout.
- **451 Unavailable For Legal Reasons**: The resource is unavailable due to legal restrictions (e.g., content blocking by law).

### Why These Codes Matter for Bug Hunters
- **4XX Codes**: These often indicate vulnerabilities, such as improperly configured permissions, exposed endpoints, or validation flaws.
- **5XX Codes**: These usually point to server misconfigurations or flaws, and can reveal weak points in server-side processing or mismanagement of resources.
- **Redirection Codes (3XX)**: They can indicate potential issues like open redirects, which might be leveraged for phishing or other attacks.
- 
---

# HTTP Auth.
Http protocol for various auth. schemes to validate users before granting access to resources. Bug hunters should be aware of these schemes to identify weaknesses or improper configurations in systems.

1. **Basic Authentication**: Sends credentials (username and password) as a Base-64 encoded string in the `Authorization` header of each HTTP request. While easy to implement, it’s vulnerable if not used over HTTPS, as the credentials can be intercepted.

2. **NTLM Authentication**: Uses the Windows NT LAN Manager (NTLM) protocol for authentication. NTLM is typically used in Windows-based environments and can be prone to vulnerabilities like relay attacks if misconfigured.

3. **Digest Authentication**: Uses MD5 hashing to create a checksum of the request, combined with a unique nonce (number used once) and the user’s credentials. This is more secure than Basic Authentication, as the password is not sent in plain text, but can still be susceptible to attacks like replay or dictionary attacks if not properly configured.


# HTTP or HTTP/s

Http is a Application layer protocol. It Stand for Hypertext transfer protocol . It work as mediator between client and server  . it tell how a client (end user) can communicate with server . It uses http request and response system . it is very basic web protocol . **it work on port 80** . It is not secure protocol because every request and response are clearly visible (vulnerable to MITM attack)  anyone can intercept the request and see the request and make changes to overcome this problem new protocol is introduced HTTP/s TLS protocol same as HTTP where s stand for Secure Socket Layer/Transport Layer protocol . It work on port **443** . It provide Secure tunnelling system so that every request it Encrypted 
HTTPs uses SSL to encrypt the data that is transferred between two parties encryption . SSL uses the RSA algorithm . 

# **HTTP Request and Response**
- **Request:** when client send some packet in order to retrieve some information or to access some resource this refer to http request .
- **Response:** when server give back reply of your request is known as response 

---

# HTTP Request Method
When client request something according to their need . It send some packet with different type of methods . These methods are pre-defined and every methods has there own work .

1. GET- 
2. POST 
3. PUT
4. HEAD
5. DELETE
6. OPTION

---

# HTTP Responses
When Server send response  of requested resource . Firstly server check ! are you an authorised person ? to access that resource . Acc. to auth. process server send response in 3 digit code . These codes are : 

1XX - information content
2XX -  Success-fully done 
3XX - Redirection of website
4XX - Client Side Error
5XX - Server side error

---

# HTTPs Auth.
Http protocol for various auth. schemes .

1. **Basic** : Send credentials as Base-64 encoded string in header of each request .
2. **NTLM :** Uses Windows NTLM protocol .
3. **Digest :**   Uses MD5 checksums of a nonce with the user’s credentials

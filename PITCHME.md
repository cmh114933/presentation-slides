## HTTP (Hyper Text Transfer Protocol)

---

### HTTP is a request-response cycle

---

## Request

+++

```
command or request 
+ optional headers 
+ optional body content.
```

+++

- `Command`, also refered to as HTTP verb denotes what type of request, it tells the server what to do with the data. Other Types:
    - `GET`
    - `POST`
    - `PUT`
    - `DELETE`
- `Headers` are 
    - optional, but typically browser/server inserts headers in to request and responses.
- `Headers` are 
    - additional information passed with the request/response, and has the following format:
    ```
        case-insensitive-name: value
    ```
    - Example:
    ```
        Accept: */*
        Authorization: Bearer XXXXXXXXXXXX
    ```

--- 

## GET Request

- Used to request data
- Parameters stored in URL
- Typically no change in database
- Body has little meaning

+++

Example:
```
GET /foo/bar?test=123 HTTP/1.1
Host: example.org
User-Agent: Mozilla/5.0 (Macintosh; U; Intel Mac OS X 10.6; fr; rv:1.9.2.8) Gecko/20100722 Firefox/3.6.8
Accept: */*
Accept-Language: fr,fr-fr;q=0.8,en-us;q=0.5,en;q=0.3
Accept-Encoding: gzip,deflate
Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7
Keep-Alive: 115
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
X-Requested-With: XMLHttpRequest
Referer: http://example.org/test
Cookie: foo=bar; lorem=ipsum;
```

---

## POST Request

- Used to send data 
- Type of data is denoted in Content-Type header
- Parameters stored in body
- Typically results in change in server/database

+++

Example:
```
POST /test HTTP/1.1
Host: foo.example
Content-Type: application/x-www-form-urlencoded
Content-Length: 27

field1=value1&field2=value2
```

+++

---

## Response

+++

```
Status code 
+ headers ( optional )
+ body ( optional )
```

+++ 
#### Status codes are split into 5 groups, each with meaning and a three digit code.
They inform the receiver of the response what the status of the response is.
```
1xx – Informational
2xx – Successful
3xx -Multiple Choice
4xx– Client Error
5xx -Server Error
```

https://www.w3.org/Protocols/rfc2616/rfc2616-sec6.html

+++ 

Example 1
```
HTTP/1.1 200 OK
Date: Mon, 27 Jul 2009 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT
Content-Length: 88
Content-Type: text/html
Connection: Closed

<html>
<body>
<h1>Hello, World!</h1>
</body>
</html>
```

+++

Example 2
```
HTTP/1.1 404 Not Found
Date: Sun, 18 Oct 2012 10:36:20 GMT
Server: Apache/2.2.14 (Win32)
Content-Length: 230
Connection: Closed
Content-Type: text/html; charset=iso-8859-1

<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html>
<head>
   <title>404 Not Found</title>
</head>
<body>
   <h1>Not Found</h1>
   <p>The requested URL /t.html was not found on this server.</p>
</body>
</html>
```

+++


---

## HTTP is Stateless (ZEN)

+++

#### Server does not store session information 
#### Every request is independent of each other

+++

- All requests originate at the client ( your browser)
- The server responds to a request.
- The requests(commands) and responses are in readable text.
- The requests are independent of each other and the server doesn’t need to track the requests.

# List of http status codes
- <https://en.wikipedia.org/wiki/List_of_HTTP_status_codes>

This is a list of *Hypertext Transfer Protocol* (HTTP) response status codes. Status codes are issued by a server in response to a *client's request* made to the server.

## 1xx information response

An information response indicates that the request was received and understood.

### 100 Continue

The server has received the request headers and the client should proceed to send the request body (in the case of a request for which a body needs to be sent; for example, a *POST* request).

### 101 Switching Protocols

The requester has asked the server to switch protocols and the server has agreed to do so.

### 102 Processing (`WebDAV`; RFC 2518)

A WebDAV request may contain many sub-requests involing file operations, requiring a long time to complete the request.

### 103 Early Hints (RFC 8297)

Used to return some response headers before final HTTP message.

## 2xx success

This class of status codes indicated the action request by the client was received, understood, and accepted.

### 200 OK

Standard response for successfull HTTP request.

### 201 Created

The request has been fulfilled, resulting in the creation of a new resource.

### 202 Accepted

The request has been accepted for processing, but the processing has not been completed.

### 203 Non-Authoritative Information (since HTTP/1.1)

The server is a transforming proxy (e.g. a *Web accelerator*) that received a 200 OK from its origin, but is returning a modified version of the origin's response.

### 204 No Content

The server successfully processed the request, and is not returning any content.

### 205 Reset Content

The server successfully processed the request, asks that the requester reset its document view, and is not returning any content.

### 206 Partial Content

The server is delivering only part of the resource (byte serving) due to a range header sent by the client.

### 207 Multi-Status (WebDAV; RFC 4918)

The message body that follows is by default an XML message and can contain a number of separate response code, depending on how many sub-requests were made.

### 208 Already Reported (WebDAV; RFC 5842)

The members of a DAV binding have already been enumerated in a preceding part of the (multistatus) response, and are not being included again.

### 226 IM Used (RFC 3229)

The server has fulfilled a request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.

## 3xx redirection

This class of status code indicates the client must take additional action to complete the request.

### 300 Multiple Choices

Indicates multiple options for the resource from which the client may choose (via *agent-driven content negotiation*).

### 301 Moved Permanently

This and all future requests should be directed to the given *URI*.

### 302 Found (Previously "Moved temporarily")

Tells the client to look at (browse to) another URL. The HTTP/1.0 specification (RFC 1945) required the client to perform a temporary redirect with the same method (the original describing phrase was "Moved Temporarily").

### 303 See Other (since HTTP/1.1)

The response to the request can be found under another *URI* using the GET method.

### 304 Not Modified

Indicates that the resource has not been modified since the version specified by the *request headers* If-Modified-Since or If-None-Match.

### 305 Use Proxy (since HTTP/1.1)

The requested resource is available only through a proxy, the address for which is provided in the response.

### 306 Switch Proxy

No longer used. Originally meant "Subsequent requests should use the specified proxy."

### 307 Temporary Redirect (since HTTP/1.1)

In this case, the request should be repeated with another URI; however, future requests should still use the original URI. In contrast to how 302 was historically implemented, the request method is not allowed to be changed when reissuing the original request.

### 308 Permananet Redirect

This and all future requests should be directed to the given *URI*. 308 parallel the behaviour of 301, but *does not allow the HTTP method to change*.

## 4xx client errors

This class of status codes is intended for situations in which the error seems to have been caused by the client.

### 400 Bad Request

The server cannot or will not process the request due to an apparent client error (e.g., malformed request syntax, size too large, invalid request message framing, or deceptive request routing).

### 401 Unauthorized

Similar to 403 Forbidden, but specifically for use when authentication is required and has faild or has not yet been provided.

### 402 Payment Required

Reserved for future use. The original intention was that this code might be used as part of some form of *digital cash* or *micropayment* scheme, as proposed, for example, by *GNU Taler*, but that has not yet happened, and this code is not widely used.

### 403 Forbidden

The request contained valid data and was understood by the server, but the server is refusing action.

### 404 Not Found

The requested resource could not be found but may be available in the future.

### 405 Method Not Allowed

A request method is not supported for the requested resource; for example, a GET request on a form that requires data to be presented via *POST*, or a PUT request on a read-only resouce.

### 406 Not Acceptable

The requested resource is capable of generating only content not acceptable according to the Accept headers sent in the request.

### 407 Proxy Authentication Required

The client must first authenticate itself with the proxy.

### 408 Request Timeout

The server timed out waiting for the request. According to HTTP specifications: "The client did not produce a request within the time that the server was prepared to wait. The client MAY repeat the request without modifications at any later time."

### 409 Conflict

Indicates that the request could not be processed because of conflict in the current state of the resource, such as an *edit conflict* between multiple simultaneous updates.

### 410 Gone

Indicates that the resource requested was previously in use but is no longer available and will not be available again.

### 411 Length Required

The request did not specify the length of its content, which is required by the requested resource.

### 412 Precondition Failed

The server does not meet one of the preconditions that the requester put on the request header fields.

### 413 Payload Too Large

The request is larger than the server is willing or able to process. Previously called "Request Entity Too Large" in RFC 2616.

### 414 URI Too Long

The *URI* provided was too long for the server to process. Often the result of too much data being encoded as a query-string of a GET request, in which case it should be converted to a POST request. Called "Request-URI Too Long" previously in RFC 2616.

### 415 Unsupported Media Type

The request entity has a *media type* which the server or resource does not support.

### 416 Range Not Satisfiable

The client has asked for a portion of the file (*byte serving*), but the server cannot supply that portion.

### 417 Expectation Failed

The server cannot meet the requirements of the Expect request-header field.

### 418 I'm a teapot (RFC 2324, RFC 7168)

This code was defined in 1998 as one of the traditional *IETF April Fool's jokes*, in RFC 2324, /Hyper Text Coffee Pot Control Protocol/, and is not expected to be implemented by actual HTTP servers.

### 421 Misdirected Request

The request was directed at a server that is not able to produce a response (for example because of connection reuse).

### 422 Unprocessable Entity

The request was well-formed but was unable to be followed due to semantic erros.

### 423 Locked (WebDAV; RFC 4918)

The resource that is being accessed is locked.

### 424 Failed Dependency (WebDAV; RFC 4918)

The request failed because it depended on another request and that request failed.

### 425 Too Early (RFC 8470)

Indicates that the server is unwilling to risk processing a request that might be replayed.

### 426 Upgrade Required

The client should switch to a different protocol such as *TLS/1.3*, given in the *Upgrade header* field.

### 428 Precondition Required (RFC 6585)

The origin server requires the request to be conditional.

### 429 Too Many Request (RFC 6585)

The user has sent too many request in a given amount of time.

### 431 Request Header Fields Too Large (RFC 6585)

The server is unwilling to process the request because either an individual header field, or all hte header fields collectively, are too large.

### 451 Unavailable For Legal Reasons (RFC 7725)

A server operator has received a legal demand to deny access to a resource or to a set of resources that includes the requested resource.

## 5xx server errors

The server fails to fulfill a request.

### 500 Internal Server Error

A generic error message, given when a unexpected condition was encountered and no more specific message is suitable.

### 501 Not Implemented

The server either does not recognize the request method, or it lacks the ability to fulfill the request.

### 502 Bad Gateway

The server was acting as a *gatewa* or proxy and received an invalid response from the upstream server.

### 503 Service Unavailable

The server cannot handle the request (because it is overloaded or down for maintenance).

### 504 Gateway Timeout

The server was acting as a gateway or proxy and did not receive a timely response from the upstream server.

### 505 HTTP Version Not Supported

The server does not support the HTTP version used in the request.

### 506 Variant Also Negotiates (RFC 2295)

Transparent *content negotiation* for the request results in a *circular reference*.

### 507 Insufficient Storage (WebDAV; RFC 4918)

The server is unable to store the representation needed to complete the request.

### 508 Loop Detected (WebDAV; RFC 5842)

The server detected an infinite loop while processing the request (sent instead of *208 Already Reported*).

### 510 Not Extended (RFC 2774)

Further extensions to the request are required for the server to fulfill it.

### 511 Network Authentication Required (RFC 6585)

The client needs to authenticate to gain network access.

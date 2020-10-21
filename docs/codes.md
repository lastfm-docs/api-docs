# Last.fm Error Codes

In addition to return [HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) along with every response from the Last.fm API, failed responses include errors. [Last.fm often does not return HTTP Status Codes that accurately reflect the state of your request](https://lastfm-docs.github.io/api-docs/bugs/#status-codes). 
This page provides a comprehensive list of error codes returned by Last.fm, along with a short description of them.

??? warning "Example response of an error"

    HTTP status: `404 NOT FOUND`
    ```json
    {
        "error": 6,
        "message": "User not found"
    }
    ```
 
 ## HTTP Status Codes Forewarning
 !!! warning
    Some API calls return HTTP 200 OK status codes even when the response contains an error.
    For this reason make sure to check your response payload to validate it.

---

### Last.fm Error Code 2: Service Unavailable/Service Unavailable
This error usually emits when Last.fm is having server issues. However this may also happen because of a malformed request with invalid endpoints.


### Last.fm Error Code 3: Invalid Method
This error emits when a request is made to an endpoint with a method that does not exist. For example, `artist.getSomeData`. While the endpoint you're making a request to might be perfectly valid, a malformed method name will prevent Last.fm from returning the data you want. For a comprehensive list of every method, refer to the API docs on this site.


### Last.fm Error Code 4: Authentication Failed
This error emits when a request is made signed with a session token that has been generated for an account that has revoked access to your application.

### Last.fm Error Code 5: Invalid Response Format
A `format` parameter is necessary in addition to the documented parameters, this may either have a value of `XML` or `JSON` (case insensitive). Requesting data in another format will emit this error. Some methods do support more than these 2 formats, the methods that do have their formats listed in this documentation.

### Last.fm Error Code 6: Parameter Error
The Last.fm API returns this error code in response to multiple types of failed request. This error can occur because:
 - Your search returned no results
 - Your request used an invalid parameter
 - Your request has a parameter with an invalid value (for example, an invalid type)
 - The requested resource is not available
 
 ### Last.fm Error Code 7: Invalid Resource Specified 
This error emits when a method requests data from a resource that does not exist, for example, an artist or album that cannot have the data you requested. This might be due to using a method that is not valid on an endpoint despite being documented.
 
### Last.fm Error Code 8: Generic Error
This error is emitted when something unexpected causes your request to fail but unfortunately Last.fm can't quite tell you what. This is a generic error. This is similar to [HTTP Error 500](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/500).

### Last.fm Error Code 9: Invalid Session Token
This error emits when a request tries to authenticate with an invalid session key, or similar missing/malformed parameters. For a guide to auth and signing your calls, refer to [this part](https://lastfm-docs.github.io/api-docs/auth/signature/) of the site. Make sure that your session key is hashed using UTF-8 encoding in addition to MD54

### Last.fm Error Code 10: Invalid API Token
This error reflects that your request was signed with an api key that is not valid. A valid API key can be generated [here](https://www.last.fm/api/account/create).

### Last.fm Error Code 11: Service Offline
Last.fm is often down and you might encounter this error when a certain part of their backend is offline. Updated for the status of Last.fm's service can be found [on this Twitter account](https://twitter.com/lastfmstatus).

### Last.fm Error Code 13: Invalid Method Signature In Request Header
This error signifies a malformed header, more specifically, one that hasn't been signed right.

### Last.fm Error Code 16: A Temporary Error Occurred 
This is another generic error similar to Last.fm error code 8, however this code implies that this request can be made again and will most likely be successful, this error usually occurs due to backed errors.

### Last.fm Error Code 26: Your API key has been banned
If you hit this error, your API key has been revoked. This can occur due to a plethora of reasons, most likely a violation of Last.fm's ratelimits multiple times, or a violation of their terms of service in general. To further clarify on why you were banned, contact Last.fm support.

### Last.fm Error Code 29: Rate Limit Exceeded 
Your IP has made too many requests in a short period. To prevent API abuse, Last.fm returns a [HTTP 429 Error](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/429) and blocks your requests. Implementing throttling might be a fair consideration.

# HTTP Status Codes
HTTP status codes returned in response headers are often useful for troubleshooting, however the Last.fm API is not held up to any standards.  __**Make sure to check your response in addition to validating your requests using HTTP headers**__.

This part of this page **does not** document every HTTP error code. You can find a comprehensive guide [here](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status).

This is meant to be a refernce for the most common HTTP codes returned by the Last.fm API

A general reference:-
  - 1** Codes : Informational responses
  - 2** Codes : Successful responses
  - 3** Codes : Redirects
  - 4** Codes : Client side errors
  - 5** Codes : Server side errors

### HTTP Status Code 200: Success
The HTTP 200 OK success status response code indicates that the request has succeeded. A 200 response is cacheable by default.
The meaning of a success depends on the HTTP request method:
   - GET: The resource has been fetched and is transmitted in the message body.
   - HEAD: The entity headers are in the message body.
   - POST: The resource describing the result of the action is transmitted in the message body.
   - TRACE: The message body contains the request message as received by the server.
The successful result of a PUT or a DELETE is often not a 200 OK but a 204 No Content (or a 201 Created when the resource is uploaded for the first time).

### HTTP Status Code 400: Bad Request
The HyperText Transfer Protocol (HTTP) 400 Bad Request response status code indicates that the server cannot or will not process the request due to something that is perceived to be a client error (e.g., malformed request syntax, invalid request message framing, or deceptive request routing).

### HTTP Status Code 403: Forbidden
The HTTP 403 Forbidden client error status response code indicates that the server understood the request but refuses to authorize it.

### HTTP Status Code 404: Not Found
The HTTP 404 Not Found client error response code indicates that the server can't find the requested resource. Links that lead to a 404 page are often called broken or dead links and can be subject to link rot.

A 404 status code does not indicate whether the resource is temporarily or permanently missing. But if a resource is permanently removed, a 410 (Gone) should be used instead of a 404 status.

### HTTP Status Code 429: Too Many Requests
The HTTP 429 Too Many Requests response status code indicates the user has sent too many requests in a given amount of time ("rate limiting").

A Retry-After header might be included to this response indicating how long to wait before making a new request.

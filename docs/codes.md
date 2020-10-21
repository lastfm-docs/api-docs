## Last.fm Error Codes

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
 
 ## HTTP Status Codes
 !!! warning
    Some API calls return HTTP 200 OK status codes even when the response contains an error.
    For this reason make sure to check your response payload to validate it.

### Last.fm Error Code 2: Service Unavailable/Service Unavailable
This error usually emits when Last.fm is having server issues. However this may also happen because of a malformed request with invalid endpoints.


### Last.fm Error Code 3: Invalid Method
This error emits when a request is made to an endpoint with a method that does not exist. For example, `artist.getSomeData`. While the endpoint you're making a request to might be perfectly valid, a malformed method name will prevent Last.fm from returning the data you want. For a comprehensive list of every method, refer to the API docs on this site.


### Last.fm Error Code 4: Authentication Failed
This error emits when a request tries to authenticate with an invalid session key, or similar missing/malformed parameters. For a guide to auth and signing your calls, refer to [this part](https://lastfm-docs.github.io/api-docs/auth/signature/) of the site. Make sure that your session key is hashed using UTF-8 encoding in addition to MD5

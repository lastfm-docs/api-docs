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

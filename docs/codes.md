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
 

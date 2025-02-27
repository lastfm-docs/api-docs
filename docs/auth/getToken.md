Get a temporary unauthorized token for an API account, this applies to non-web application authorization only.

## Parameters
| Method | Type | Default | Required | Description
| ------ | ---- | ------- | -------- | -----------
| `api_key` | [string][string] | `none` | :white_check_mark: | A Last.fm API key.
| `api_sig` | [string][string] | `none` | :white_check_mark: | A Last.fm method signature, see [signature](signature.md)

## Respones
Errors:  

- 8 : There was an error granting the request token. Please try again later  
- 2 : Invalid service - This service does not exist  
- 3 : Invalid Method - No method with that name in this package  
- 4 : Authentication Failed - You do not have permissions to access the service  
- 5 : Invalid format - This service doesn't exist in that format  
- 6 : Invalid parameters - Your request is missing a required parameter  
- 7 : Invalid resource specified  
- 8 : Operation failed - Something else went wrong  
- 9 : Invalid session key - Please re-authenticate  
- 10 : Invalid API key - You must be granted a valid key by last.fm  
- 11 : Service Offline - This service is temporarily offline. Try again later.  
- 13 : Invalid method signature supplied  
- 16 : There was a temporary error processing your request. Please try again  
- 26 : Suspended API key - Access for your account has been suspended, please contact Last.fm  
- 29 : Rate limit exceeded - Your IP has made too many requests in a short period  

## Examples

??? note "Example XML response"
    | Parameter | Value         |
    | --------- | ------------- |
    | api_key   | YOUR_API_KEY  |

    HTTP status: `200 OK`
    ```
    http://ws.audioscrobbler.com/2.0/?method=auth.gettoken&api_key=YOUR_API_KEY&format=json
    ```
    ```xml
      <lfm status="ok">
        <token>cf45fe5a3e3cebe168480a086d7fe481</token>
      </lfm>
    ```

??? note "Example JSON response" 
    | Parameter | Value         |
    | --------- | ------------- |
    | api_key   | YOUR_API_KEY  |
    | format    | json          |
    
    HTTP status: `200 OK`
    ```
    http://ws.audioscrobbler.com/2.0/?method=auth.gettoken&api_key=YOUR_API_KEY
    ```
    ```json
      {
        "token":"cf45fe5a3e3cebe168480a086d7fe481"
      }
    ```

??? note "What to do with the token?" 
    This token can then be used to authenticate a user by requesting the user to authorize via the auth link, with this token and your api key as parameter.

    | Parameter | Value           |
    | --------- | --------------- |
    | api_key   | YOUR_API_KEY    |
    | token     | REQUESTED_TOKEN |
    | format    | json          |
    
    ```
    http://www.last.fm/api/auth/?api_key=YOUR_API_KEY&token=REQUESTED_TOKEN&format=json
    ```

    After the user has authorized via this url you can use [getSession](getSession.md)


[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
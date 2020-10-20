Returns profile information about a last.fm user.

This method doesn't not require authentication.

## Parameters

| Method     | Type                                                                                                | Default                  | Optional                      | Description                                                                                                                        |
| ---------- | --------------------------------------------------------------------------------------------------- | ------------------------ | ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `user`     | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)   | `none`                   | :negative_squared_cross_mark: | The last.fm username to fetch the recent tracks of                                                                                 |
| `api_key`  | [token](https://www.last.fm/api/account/create)                                                     | `none`                   | :negative_squared_cross_mark: | A Last.fm API key.                                                                                                                 |

## Responses

Errors:

- 6 : Invalid parameters - Your request is missing a required parameter
- 8 : Operation failed - Something else went wrong
- 10 : Invalid API key - You must be granted a valid key by last.fm
- 11 : Service Offline - This service is temporarily offline. Try again later.
- 13 : Invalid method signature supplied
- 16 : There was a temporary error processing your request. Please try again
- 17 : Login required - Requested profile might not have privacy set to public.
- 26 : Suspended API key - Access for your account has been suspended, please contact Last.fm
- 29 : Rate limit exceeded - Your IP has made too many requests in a short period

## Examples

??? note "Example response"

    | Parameter | Value          |
    |-----------|----------------|
    | username  | TyphoonsNotABot|
    | format    | json           |
    
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=user.getinfo&user=TyphoonsNotABot&api_key=YOUR_API_KEY&format=json
    ```

    ```json
      {
        "user": {
          "playlists": "0",
          "playcount": "138223",
          "gender": "n",
          "name": "TyphoonsNotABot",
          "subscriber": "0",
          "url": "https://www.last.fm/user/TyphoonsNotABot",
          "country": "United Kingdom",
          "image": [
            {
              "size": "small",
              "#text": "https://lastfm.freetls.fastly.net/i/u/34s/9e9565eee02f3e08d803b7726f65f406.png"
            },
            {
              "size": "medium",
              "#text": "https://lastfm.freetls.fastly.net/i/u/64s/9e9565eee02f3e08d803b7726f65f406.png"
            },
            {
              "size": "large",
              "#text": "https://lastfm.freetls.fastly.net/i/u/174s/9e9565eee02f3e08d803b7726f65f406.png"
            },
            {
              "size": "extralarge",
              "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/9e9565eee02f3e08d803b7726f65f406.png"
            }
          ],
          "registered": {
            "unixtime": "1561177193",
            "#text": 1561177193
          },
          "type": "user",
          "age": "0",
          "bootstrap": "0",
          "realname": "Liam"
        }
      }
    ```

??? warning "Example response of non existing user"

    HTTP status: `404 NOT FOUND`

    ```
    https://ws.audioscrobbler.com/2.0/?method=user.getinfo&user=userthatdoesnotexist&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
        "error": 6,
        "message": "User not found"
    }
    ```

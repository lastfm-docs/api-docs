A paginated list of all the artists in a user's library, with play counts and tag counts.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `user` | [string][string] | `none` | :white_check_mark: | The user whose library you want to fetch.
| `limit` | [number][number] | 50  | :negative_squared_cross_mark: | The number of results to fetch per page. Maximum 2000.
| `page` | [number][number] | 1 | :negative_squared_cross_mark: | The page number to fetch.
| `api_key` | [key][key] | `none` | :white_check_mark: | A Last.fm API key.

## Responses
Errors:

- 6 : Invalid parameters - Your request was either missing a required parameter, the parameter was not found, or had 0 results
- 8 : Operation failed - Something else went wrong  
- 9 : Invalid session key - Please re-authenticate  
- 10 : Invalid API key - You must be granted a valid key by last.fm  
- 11 : Service Offline - This service is temporarily offline. Try again later.  
- 13 : Invalid method signature supplied  
- 16 : There was a temporary error processing your request. Please try again  
- 26 : Suspended API key - Access for your account has been suspended, please contact Last.fm  
- 29 : Rate limit exceeded - Your IP has made too many requests in a short period  

## Examples
??? note "Example response"

    | Parameter | Value |
    | --------- | ----- |
    | user      | aidan- |
    | limit     | 2 |
    | api_key   | YOUR_API_KEY |
    | format    | json  |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=library.getartists&api_key=YOUR_API_KEY&format=json&limit=2&user=aidan-
    ```

    ```json
    {
        "artists": {
            "artist": [
            {
                "url": "https://www.last.fm/music/Queen",
                "mbid": "5eecaf18-02ec-47af-a4f2-7831db373419",
                "tagcount": "0",
                "playcount": "1511",
                "streamable": "0",
                "name": "Queen",
                "image": [
                {
                    "size": "small",
                    "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                    "size": "medium",
                    "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                    "size": "large",
                    "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                    "size": "extralarge",
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                    "size": "mega",
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png"
                }
                ]
            },
            {
                "url": "https://www.last.fm/music/Videoclub",
                "mbid": "f4903035-e9cd-4b7f-b462-0447b0cd490a",
                "tagcount": "0",
                "playcount": "1123",
                "streamable": "0",
                "name": "Videoclub",
                "image": [
                {
                    "size": "small",
                    "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                    "size": "medium",
                    "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                    "size": "large",
                    "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                    "size": "extralarge",
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                    "size": "mega",
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png"
                }
                ]
            }
            ],
            "@attr": {
            "page": "1",
            "total": "1931",
            "user": "aidan-",
            "perPage": "2",
            "totalPages": "966"
            }
        }
    }
    
    ```

!!! warning
    To use parameters: `from` and `to`, you must declare **both** of them otherwise it will be treated with no start or end date

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create
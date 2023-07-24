Get a track chart for a user profile, for a given date range. If no date range is supplied, it will return the most recent track chart for this user.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `user` | [string][string] | `none` | :white_check_mark: | The Last.fm username to fetch the friends of.
| `limit` | [number][number] | `none` | :negative_squared_cross_mark: | The number of results to fetch. Maximum 1000.
| `from` | [number][number] | `UNIX timestamp of the seventh most recent time it was 12pm (UTC)` | :negative_squared_cross_mark: | The date at which the chart should start from (can preceed a week).
| `to` | [number][number] | `UNIX timestamp of the last time it was 12pm (UTC)` | :negative_squared_cross_mark: | The date at which the chart should end on.
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

    | Parameter | Value        |
    | --------- | ------------ |
    | user      | aidan-       |
    | limit     | 2            |
    | api_key   | YOUR_API_KEY |
    | format    | json         |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=user.getWeeklyTrackChart&user=aidan-&limit=2&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
    "weeklytrackchart": {
        "@attr": {
        "user": "aidan-",
        "from": "1602504000",
        "to": "1603108800"
        },
        "track": [
        {
            "artist": {
            "mbid": "cc0b7089-c08d-4c10-b6b0-873582c17fd6",
            "#text": "System of a Down"
            },
            "@attr": {
            "rank": "1"
            },
            "mbid": "0f1f8fdb-d14b-4629-8c29-43f041d52f88",
            "url": "https://www.last.fm/music/System+of+a+Down/_/Kill+Rock+%27n+Roll",
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
            }
            ],
            "name": "Kill Rock 'n Roll",
            "playcount": "176"
        },
        {
            "artist": {
            "mbid": "cc0b7089-c08d-4c10-b6b0-873582c17fd6",
            "#text": "System of a Down"
            },
            "@attr": {
            "rank": "2"
            },
            "mbid": "145977d0-21c8-449a-b11c-1e2f96e26af3",
            "url": "https://www.last.fm/music/System+of+a+Down/_/Stealing+Society",
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
            }
            ],
            "name": "Stealing Society",
            "playcount": "51"
        }
        ]
    }
    }
    
    ```

!!! warning
    To use parameters: `from` and `to`, you must declare **both** of them otherwise it will be treated with no start or end date

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create
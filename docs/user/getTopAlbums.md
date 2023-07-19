Get the top albums listened to by a user. You can stipulate a time period. Sends the overall chart by default.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `user` | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none` | :white_check_mark: | The last.fm username to fetch top albums for.
| `period` | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | overall | :negative_squared_cross_mark: | The time period over which to retrieve top albums for. Can be `overall`, `7day`, `1month`, `3month`, `6month` or `12month`.
| `limit` | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 50 | :negative_squared_cross_mark: | The number of results to fetch per page. Defaults to 50.
| `page` | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 1       | :negative_squared_cross_mark:      | The page number to fetch. Defaults to first page.
| `api_key` | [token](https://www.last.fm/api/account/create) | `none` | :white_check_mark: | A Last.fm API key.

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
    | username  | aidan-|
    | limit     | 3     |
    | format    | json  |

    HTTP status: `200 OK`

    ```
    http://ws.audioscrobbler.com/2.0/?api_key=YOUR_API_KEY&method=user.getTopAlbums&user=aidan-&format=json&limit=10
    ```

    ```json
    {
        "topalbums": {
            "album": [
                {
                    "artist": {
                        "url": "https://www.last.fm/music/Joy+Division",
                        "name": "Joy Division",
                        "mbid": "9a58fda3-f4ed-4080-a3a5-f457aac9fcdd"
                    },
                    "@attr": {
                        "rank": "1"
                    },
                    "image": [
                        {
                            "size": "small",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/34s/043311d565be4296bb13f299ba1f08de.jpg"
                        },
                        {
                            "size": "medium",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/64s/043311d565be4296bb13f299ba1f08de.jpg"
                        },
                        {
                            "size": "large",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/174s/043311d565be4296bb13f299ba1f08de.jpg"
                        },
                        {
                            "size": "extralarge",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/043311d565be4296bb13f299ba1f08de.jpg"
                        }
                    ],
                    "playcount": "596",
                    "url": "https://www.last.fm/music/Joy+Division/The+Best+Of",
                    "name": "The Best Of",
                    "mbid": ""
                },
                {
                    "artist": {
                        "url": "https://www.last.fm/music/Lily+Allen",
                        "name": "Lily Allen",
                        "mbid": "6e0c7c0e-cba5-4c2c-a652-38f71ef5785d"
                    },
                    "@attr": {
                        "rank": "2"
                    },
                    "image": [
                        {
                            "size": "small",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/34s/13ac538c05b22f5d4f5290d4740b59f4.png"
                        },
                        {
                            "size": "medium",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/64s/13ac538c05b22f5d4f5290d4740b59f4.png"
                        },
                        {
                            "size": "large",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/174s/13ac538c05b22f5d4f5290d4740b59f4.png"
                        },
                        {
                            "size": "extralarge",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/13ac538c05b22f5d4f5290d4740b59f4.png"
                        }
                    ],
                    "playcount": "484",
                    "url": "https://www.last.fm/music/Lily+Allen/It%27s+Not+Me,+It%27s+You+(Special+Edition)",
                    "name": "It's Not Me, It's You (Special Edition)",
                    "mbid": ""
                },
                {
                    "artist": {
                        "url": "https://www.last.fm/music/System+of+a+Down",
                        "name": "System of a Down",
                        "mbid": "cc0b7089-c08d-4c10-b6b0-873582c17fd6"
                    },
                    "@attr": {
                        "rank": "3"
                    },
                    "image": [
                        {
                            "size": "small",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/34s/e0ea42e8dd3e4f1aaa61a7bd0c833117.png"
                        },
                        {
                            "size": "medium",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/64s/e0ea42e8dd3e4f1aaa61a7bd0c833117.png"
                        },
                        {
                            "size": "large",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/174s/e0ea42e8dd3e4f1aaa61a7bd0c833117.png"
                        },
                        {
                            "size": "extralarge",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/e0ea42e8dd3e4f1aaa61a7bd0c833117.png"
                        }
                    ],
                    "playcount": "482",
                    "url": "https://www.last.fm/music/System+of+a+Down/Hypnotize",
                    "name": "Hypnotize",
                    "mbid": "0c63d2e4-2a99-4cc4-8991-a88dba182bbd"
                }
            ],
            "@attr": {
                "page": "1",
                "total": "3344",
                "user": "aidan-",
                "perPage": "3",
                "totalPages": "1115"
            }
        }
    }
    
    ```

Get the top tracks listened to by a user. You can stipulate a time period. Sends the overall chart by default.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `user` | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none` | :white_check_mark: | The Last.fm username to fetch top tracks for.
| `period` | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | overall | :negative_squared_cross_mark: | The time period over which to retrieve top albums for. Can be `overall`, `7day`, `1month`, `3month`, `6month` or `12month`.
| `limit` | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 50 | :negative_squared_cross_mark: | The number of results to fetch per page. Defaults to 50.
| `page` | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 1 | :negative_squared_cross_mark: | The page number to fetch. Defaults to the first page.
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
    https://ws.audioscrobbler.com/2.0/?method=user.getTopTracks&user=aidan-&api_key=YOUR_API_KEY&format=json&limit=3
    ```

    ```json
    {
        "toptracks": {
            "@attr": {
                "page": "1",
                "total": "5171",
                "user": "aidan-",
                "perPage": "3",
                "totalPages": "1724"
            },
            "track": [
                {
                    "@attr": {
                        "rank": "1"
                    },
                    "duration": "205",
                    "playcount": "440",
                    "artist": {
                        "url": "https://www.last.fm/music/Joy+Division",
                        "name": "Joy Division",
                        "mbid": "9a58fda3-f4ed-4080-a3a5-f457aac9fcdd"
                    },
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
                        }
                    ],
                    "streamable": {
                        "fulltrack": "0",
                        "#text": "0"
                    },
                    "mbid": "00046764-a84c-3568-b8b1-6a8174f7ca0b",
                    "name": "Love Will Tear Us Apart",
                    "url": "https://www.last.fm/music/Joy+Division/_/Love+Will+Tear+Us+Apart"
                },
                {
                    "@attr": {
                        "rank": "2"
                    },
                    "duration": "222",
                    "playcount": "399",
                    "artist": {
                        "url": "https://www.last.fm/music/Videoclub",
                        "name": "Videoclub",
                        "mbid": "f4903035-e9cd-4b7f-b462-0447b0cd490a"
                    },
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
                        }
                    ],
                    "streamable": {
                        "fulltrack": "0",
                        "#text": "0"
                    },
                    "mbid": "f2d3087b-913d-41e4-aa94-0c207fd30d1d",
                    "name": "Roi",
                    "url": "https://www.last.fm/music/Videoclub/_/Roi"
                },
                {
                    "@attr": {
                        "rank": "3"
                    },
                    "duration": "193",
                    "playcount": "352",
                    "artist": {
                        "url": "https://www.last.fm/music/Clara+Luciani",
                        "name": "Clara Luciani",
                        "mbid": "a6386935-e6ee-4aaa-aaa8-70f56b79bc29"
                    },
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
                        }
                    ],
                    "streamable": {
                        "fulltrack": "0",
                        "#text": "0"
                    },
                    "mbid": "03b34579-3c04-4c34-a203-728500e95f52",
                    "name": "La grenade",
                    "url": "https://www.last.fm/music/Clara+Luciani/_/La+grenade"
                }
            ]
        }
    }
    
    ```

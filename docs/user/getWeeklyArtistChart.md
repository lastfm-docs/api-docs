Get an artist chart for a user profile, for a given date range. If no date range is supplied, it will return the most recent artist chart for this user.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `user` | [string][string] | `none` | :negative_squared_cross_mark: | The Last.fm username to fetch the charts of.
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
    https://ws.audioscrobbler.com/2.0/?method=user.getWeeklyArtistChart&user=aidan-&limit=2&api_key=YOUR_API_KEY&format=json
    ```

    ```json
        {
            "weeklyartistchart": {
                "artist": [
                    {
                        "@attr": {
                            "rank": "1"
                        },
                        "mbid": "cc0b7089-c08d-4c10-b6b0-873582c17fd6",
                        "playcount": "572",
                        "name": "System of a Down",
                        "url": "https://www.last.fm/music/System+of+a+Down"
                    },
                    {
                        "@attr": {
                            "rank": "2"
                        },
                        "mbid": "d41a6875-b626-4c0f-89a1-aecb643d29ff",
                        "playcount": "165",
                        "name": "The Pogues",
                        "url": "https://www.last.fm/music/The+Pogues"
                    }
                ],
                "@attr": {
                    "user": "aidan-",
                    "from": "1602504000",
                    "to": "1603108800"
                }
            }
        }
    
    ```

!!! warning
    To use parameters: `from` and `to`, you must declare **both** of them otherwise it will be treated with no start or end date

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create
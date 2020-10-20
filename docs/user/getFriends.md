#getFriends

Get a list of the user's friends (follow each other) on Last.fm.

No authentication required.

##Parameters
| Parameter      | Required           | Description                                            |
| -------------- | ------------------ | ------------------------------------------------------ |
| `user`         | :white_check_mark: | The last.fm username to fetch the friends of.
| `recenttracks` |                    | Whether or not to include information about friends' recent listening in the response.
| `limit`        |                    | The number of results to fetch per page. Defaults to 50.
| `page`         |                    | The page number to fetch. Defaults to first page.


## Responses
Errors:

- 8 : Operation failed - Something else went wrong  
- 9 : Invalid session key - Please re-authenticate  
- 10 : Invalid API key - You must be granted a valid key by last.fm  
- 11 : Service Offline - This service is temporarily offline. Try again later.  
- 13 : Invalid method signature supplied  
- 16 : There was a temporary error processing your request. Please try again  
- 26 : Suspended API key - Access for your account has been suspended, please contact Last.fm  
- 29 : Rate limit exceeded - Your IP has made too many requests in a short period  


## Examples
??? note "Example response (limit 1)"

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?api_key=CENSORED&method=User.getfriends&user=aidan-&format=json&limit=1
    ```

    ```json
    {
        "friends":{
            "user": [
                {
                    "playlists": "0",
                    "playcount": "4",
                    "subscriber": "0",
                    "name": "oldmaneatintwix",
                    "country": "United Kingdom",
                    "image": [
                        {
                            "size": "small",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/34s/1c3fd3c2548906f6ea0f2863718c2668.png"
                        },
                        {
                            "size": "medium",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/64s/1c3fd3c2548906f6ea0f2863718c2668.png"
                        },
                        {
                            "size": "large",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/174s/1c3fd3c2548906f6ea0f2863718c2668.png"
                        },
                        {
                            "size": "extralarge",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/1c3fd3c2548906f6ea0f2863718c2668.png"
                        }
                    ],
                    "registered": {
                        "unixtime": "1603189685",
                        "#text": "2020-10-20 10:28"
                    },
                    "url": "https://www.last.fm/user/oldmaneatintwix",
                    "realname": "Charlie Brown",
                    "bootstrap": "0",
                    "type": "user"
                }
            ],
            "@attr": {
                "page": "1",
                "total": "10",
                "user": "aidan-",
                "perPage": "1",
                "totalPages": "10"
            }
        }
    }
    
    ```



??? warning "Example response of non existing user"
    HTTP status: `404 NOT FOUND`

    ```
    https://ws.audioscrobbler.com/2.0/?api_key=CENSORED&method=User.getfriends&user=userthatdoesntexist&format=json
    ```

    ```json
    {
        "error": 6,
        "message": "User not found"
    }
    ```

??? warning "Example response of a user with no friends"
    HTTP status: `400 BAD REQUEST`

    ```
    https://ws.audioscrobbler.com/2.0/?api_key=CENSORED&method=User.getfriends&user=letmeridee&format=json
    ```

    ```json
    {
        "error": 6,
        "message": "User not found"
    }
    ```

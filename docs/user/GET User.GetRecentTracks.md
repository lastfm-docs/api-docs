Get a list of the recent tracks listened to by this user. Adds the currently playing track with the `"nowplaying":"true"` attribute if the user is currently listening.

No authentication required.

## Parameters


| Method      | Required          | Example    | Description                               |
| ----------- | ------------------|----------- | ------------------------------------------|
| `user`      | :white_check_mark:| frikandel_ | The last.fm username to fetch the recent tracks of
| `limit`     |                   | 10         | The number of results to fetch per page. Defaults to 50. Maximum is 1000. One track is added when the user is currently listening.
| `page`      |                   | 2          | The page number to fetch. Defaults to first page.
| `from`      |                   | 1577836800 | Beginning timestamp of a range - only display scrobbles after this time, in UNIX timestamp format. Timezone is UTC.
| `to`        |                   | 1606780800 | End timestamp of a range - only display scrobbles before this time, in UNIX timestamp format (num of seconds). Timezone is UTC.
| `extended`  |                   | 1          | Whether to include extra data. This data is artist info and if the user has loved a track. Changes the output format.

TODO: Add parameters for authorized call


## Responses

Errors:

- 6 : Invalid parameters - Your request is missing a required parameter
- 8 : Operation failed - Something else went wrong
- 9 : Invalid session key - Please re-authenticate
- 10 : Invalid API key - You must be granted a valid key by last.fm
- 11 : Service Offline - This service is temporarily offline. Try again later.
- 13 : Invalid method signature supplied
- 16 : There was a temporary error processing your request. Please try again
- 17 : Login required - Requested profile might not have privacy set to public.
- 26 : Suspended API key - Access for your account has been suspended, please contact Last.fm
- 29 : Rate limit exceeded - Your IP has made too many requests in a short period

## Examples


??? note "Example response of 1 track (limit 1, user not playing)"

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?api_key=censored&method=User.getrecenttracks&user=frikandel_&format=json&limit=1
    ```

    ```json
    {
        "recenttracks": {
            "@attr": {
                "page": "1",
                "total": "94618",
                "user": "frikandel_",
                "perPage": "1",
                "totalPages": "94618"
            },
            "track": [
                {
                    "artist": {
                        "mbid": "63aa26c3-d59b-4da4-84ac-716b54f1ef4d",
                        "#text": "Tame Impala"
                    },
                    "album": {
                        "mbid": "0d2cb66c-3a32-4f81-b977-9231c461c34a",
                        "#text": "Lonerism"
                    },
                    "image": [
                        {
                            "size": "small",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/34s/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        },
                        {
                            "size": "medium",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/64s/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        },
                        {
                            "size": "large",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/174s/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        },
                        {
                            "size": "extralarge",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        }
                    ],
                    "streamable": "0",
                    "date": {
                        "uts": "1603188238",
                        "#text": "20 Oct 2020, 10:03"
                    },
                    "url": "https://www.last.fm/music/Tame+Impala/_/Feels+Like+We+Only+Go+Backwards",
                    "name": "Feels Like We Only Go Backwards",
                    "mbid": "1587517a-9b2b-385a-b044-673fddf88004"
                }
            ]
        }
    }
    ```

??? note "Example response of 2 tracks (limit 1, extended 1, user now playing)"

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?api_key=censored&method=User.getrecenttracks&user=frikandel_&format=json&limit=1&extended=1
    ```

    ```json
    {
        "recenttracks": {
            "@attr": {
                "page": "1",
                "total": "94613",
                "user": "frikandel_",
                "perPage": "1",
                "totalPages": "94613"
            },
            "track": [
                {
                    "@attr": {
                        "nowplaying": "true"
                    },
                    "artist": {
                        "url": "https://www.last.fm/music/Tame+Impala",
                        "mbid": "",
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
                        "name": "Tame Impala"
                    },
                    "mbid": "08b8e930-fa2d-454d-a659-069df6111a02",
                    "image": [
                        {
                            "size": "small",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/34s/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        },
                        {
                            "size": "medium",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/64s/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        },
                        {
                            "size": "large",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/174s/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        },
                        {
                            "size": "extralarge",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        }
                    ],
                    "url": "https://www.last.fm/music/Tame+Impala/_/Apocalypse+Dreams",
                    "streamable": "0",
                    "album": {
                        "mbid": "0d2cb66c-3a32-4f81-b977-9231c461c34a",
                        "#text": "Lonerism"
                    },
                    "name": "Apocalypse Dreams",
                    "loved": "0"
                },
                {
                    "mbid": "0632aa27-3c1f-4ca9-ae87-e656ce677bfe",
                    "loved": "0",
                    "artist": {
                        "url": "https://www.last.fm/music/Tame+Impala",
                        "mbid": "",
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
                        "name": "Tame Impala"
                    },
                    "image": [
                        {
                            "size": "small",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/34s/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        },
                        {
                            "size": "medium",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/64s/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        },
                        {
                            "size": "large",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/174s/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        },
                        {
                            "size": "extralarge",
                            "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/7c9c4d1009514b178c82f2201e3a1fce.jpg"
                        }
                    ],
                    "date": {
                        "uts": "1603186824",
                        "#text": "20 Oct 2020, 09:40"
                    },
                    "streamable": "0",
                    "url": "https://www.last.fm/music/Tame+Impala/_/Endors+Toi",
                    "name": "Endors Toi",
                    "album": {
                        "mbid": "0d2cb66c-3a32-4f81-b977-9231c461c34a",
                        "#text": "Lonerism"
                    }
                }
            ]
        }
    }
    ```


??? warning "Example response of non existing user"
    HTTP status: `404 NOT FOUND`

    ```
    https://ws.audioscrobbler.com/2.0/?api_key=censored&method=User.getrecenttracks&user=userthatdoesntexist&format=json
    ```

    ```json
    {
        "error": 6,
        "message": "User not found"
    }
    ```

    
??? warning "Example response of user with 'Hide recent listening information' enabled"
    HTTP status: `403 FORBIDDEN`

    ```
    https://ws.audioscrobbler.com/2.0/?api_key=censored&method=User.getrecenttracks&user=frikandel_&format=json
    ```

    ```json
    {
        "error": 17,
        "message": "Login: User required to be logged in"
    }
    ```

TODO: Add example of authorized call
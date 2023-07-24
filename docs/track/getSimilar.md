Get the similar tracks for this track on Last.fm, based on listening data.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description
| ------ | ---- | ------- | -------- | -----------
| `artist` | [string][string] | `none` | :white_check_mark: \* | The artist name to fetch information for.
| `track` | [string][string] | `none` | :white_check_mark: \* | The track name to fetch information for.
| `mbid` | [string][string] | `none` | :negative_squared_cross_mark: | The artist's MusicBrainz ID.
| `autocorrect` | [number][number] | 0 | :negative_squared_cross_mark: | Transform misspelled artist names into correct artist names, returning the correct version instead. The corrected artist name will be returned in the response.
| `limit` | [number][number] | 100 | :negative_squared_cross_mark: | The number of results to fetch per page.
| `api_key` | [key][key] | `none` | :white_check_mark: | A Last.fm API key.

\* Required unless you are using a MusicBrainz ID for the artist/track.

## Responses
Errors:

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

!!! Warning
    This API call returns 200 OK HTTP status codes even when the response contains an error.

## Examples

??? note "Example response"

    | Parameter | Value        |
    | --------- | ------------ |
    | artist    | Disturbed    |
    | track     | Stricken     |
    | api_key   | YOUR_API_KEY |
    | format    | json         |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=track.getSimilar&artist=Disturbed&track=Stricken&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "similartracks": {
        "track": [
          {
            "name": "Down With the Sickness",
            "playcount": 8066450,
            "mbid": "a8009036-b13e-4cb8-b2c7-2c3f9735b735",
            "match": 1,
            "url": "https://www.last.fm/music/Disturbed/_/Down+With+the+Sickness",
            "streamable": {
              "#text": "0",
              "fulltrack": "0"
            },
            "duration": 278,
            "artist": {
              "name": "Disturbed",
              "mbid": "dc75517c-d268-486d-bd5b-0eaff34eeef9",
              "url": "https://www.last.fm/music/Disturbed"
            },
            "image": [
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "small"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "medium"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "large"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "extralarge"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "mega"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": ""
              }
            ]
          },
          {
            "name": "Inside the Fire",
            "playcount": 3983007,
            "mbid": "38c28d49-c0e4-4700-93d4-1c834400fe35",
            "match": 0.976467,
            "url": "https://www.last.fm/music/Disturbed/_/Inside+the+Fire",
            "streamable": {
              "#text": "0",
              "fulltrack": "0"
            },
            "duration": 233,
            "artist": {
              "name": "Disturbed",
              "mbid": "dc75517c-d268-486d-bd5b-0eaff34eeef9",
              "url": "https://www.last.fm/music/Disturbed"
            },
            "image": [
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "small"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "medium"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "large"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "extralarge"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "mega"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": ""
              }
            ]
          },
          {
            "name": "Before I Forget",
            "playcount": 9225371,
            "mbid": "0692129f-cfb5-4ca2-a2a5-e2c03251388f",
            "match": 0.602882,
            "url": "https://www.last.fm/music/Slipknot/_/Before+I+Forget",
            "streamable": {
              "#text": "0",
              "fulltrack": "0"
            },
            "duration": 263,
            "artist": {
              "name": "Slipknot",
              "mbid": "ceb7b6be-1dbb-4d80-b157-5588bc884764",
              "url": "https://www.last.fm/music/Slipknot"
            },
            "image": [
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "small"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "medium"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "large"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "extralarge"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": "mega"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                "size": ""
              }
            ]
          },
          ... and 97 more
        ],
        "@attr": {
          "artist": "Disturbed"
        }
      }
    }
    ```

??? warning "Example response of a track/artist that doesnt exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=track.getSimilar&artist=Fake+Artist&track=Fake+Track&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "similartracks": {
        "track": [],
        "@attr": {
          "artist": "Fake Artist"
        }
      }
    }
    ```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create
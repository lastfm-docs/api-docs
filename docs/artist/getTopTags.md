Get the top tags for an artist on Last.fm, ordered by popularity.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `artist` | [string][string] | `none` | :white_check_mark: \* | The artist name to fetch information for.
| `mbid` | [string][string] | `none` | :negative_squared_cross_mark: | The artist's MusicBrainz ID.
| `autocorrect` | [number][number] | 0 | :negative_squared_cross_mark: | Transform misspelled artist names into correct artist names, returning the correct version instead. The corrected artist name will be returned in the response.
| `api_key` | [key][key] | `none` | :white_check_mark: | A Last.fm API key.

\* Required unless you are using a MusicBrainz ID for the artist.

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

	| Parameter | Value         |
	| --------- | ------------- |
	| artist    | Audioslave    |
	| api_key   | YOUR_API_KEY  |
	| format    | json          |

	HTTP status: `200 OK`

	```
	https://ws.audioscrobbler.com/2.0/?method=artist.getTopTags&artist=Audioslave&api_key=YOUR_API_KEY&format=json
	```
	```json
	{
		"toptags": {
			"tag": [
				{
					"count": 100,
					"name": "rock",
					"url": "https://www.last.fm/tag/rock"
				},
				{
					"count": 78,
					"name": "alternative rock",
					"url": "https://www.last.fm/tag/alternative+rock"
				},
				{
					"count": 52,
					"name": "hard rock",
					"url": "https://www.last.fm/tag/hard+rock"
				},
				{
					"count": 46,
					"name": "alternative",
					"url": "https://www.last.fm/tag/alternative"
				},
				{
					"count": 41,
					"name": "Grunge",
					"url": "https://www.last.fm/tag/Grunge"
				},
				{
					"count": 19,
					"name": "seen live",
					"url": "https://www.last.fm/tag/seen+live"
				},
				{
					"count": 10,
					"name": "post-grunge",
					"url": "https://www.last.fm/tag/post-grunge"
				},
				{
					"count": 8,
					"name": "metal",
					"url": "https://www.last.fm/tag/metal"
				},
				{
					"count": 8,
					"name": "Audioslave",
					"url": "https://www.last.fm/tag/Audioslave"
				},
				{
					"count": 5,
					"name": "american",
					"url": "https://www.last.fm/tag/american"
				},
				{
					"count": 4,
					"name": "Chris Cornell",
					"url": "https://www.last.fm/tag/Chris+Cornell"
				},
				{
					"count": 4,
					"name": "indie",
					"url": "https://www.last.fm/tag/indie"
				},
				{
					"count": 3,
					"name": "00s",
					"url": "https://www.last.fm/tag/00s"
				},
				{
					"count": 3,
					"name": "alternative metal",
					"url": "https://www.last.fm/tag/alternative+metal"
				},
				{
					"count": 3,
					"name": "Supergroup",
					"url": "https://www.last.fm/tag/Supergroup"
				},
				{
					"count": 2,
					"name": "indie rock",
					"url": "https://www.last.fm/tag/indie+rock"
				},
				{
					"count": 2,
					"name": "Progressive rock",
					"url": "https://www.last.fm/tag/Progressive+rock"
				},
				{
					"count": 2,
					"name": "heavy metal",
					"url": "https://www.last.fm/tag/heavy+metal"
				},
				{
					"count": 2,
					"name": "classic rock",
					"url": "https://www.last.fm/tag/classic+rock"
				},
				{
					"count": 2,
					"name": "Post Grunge",
					"url": "https://www.last.fm/tag/Post+Grunge"
				},
				{
					"count": 2,
					"name": "punk",
					"url": "https://www.last.fm/tag/punk"
				},
				{
					"count": 2,
					"name": "favorites",
					"url": "https://www.last.fm/tag/favorites"
				},
				{
					"count": 2,
					"name": "tom morello",
					"url": "https://www.last.fm/tag/tom+morello"
				},
				{
					"count": 1,
					"name": "USA",
					"url": "https://www.last.fm/tag/USA"
				},
				{
					"count": 1,
					"name": "funk",
					"url": "https://www.last.fm/tag/funk"
				},
				{
					"count": 1,
					"name": "male vocalists",
					"url": "https://www.last.fm/tag/male+vocalists"
				}
			],
			"@attr": {
				"artist": "Audioslave"
			}
		}
	}
	```

??? warning "Example response of an artist/track that doesnt exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=artist.getTopTags&artist=artistthatdoesntexist&api_key=YOUR_API_KEY&format=json
    ```
		```json
		{
			"error": 6,
			"message": "The artist you supplied could not be found",
			"links": []
		}
		```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create

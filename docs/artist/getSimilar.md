Get all the artists similar to this artist.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `artist` | [string][string] | `none` | :white_check_mark: \* | The artist name to fetch information for.
| `mbid` | [string][string] | `none` | :negative_squared_cross_mark: | The artist's MusicBrainz ID.
| `autocorrect` | [number][number] | 0 | :negative_squared_cross_mark: | Transform misspelled artist names into correct artist names, returning the correct version instead. The corrected artist name will be returned in the response.
| `limit` | [number][number] | 30 | :negative_squared_cross_mark: | The number of results to fetch per page.
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
	| artist    | Metallica     |
	| api_key   | YOUR_API_KEY  |
	| format    | json          |

	HTTP status: `200 OK`

	```
	https://ws.audioscrobbler.com/2.0/?method=artist.getSimilar&artist=Metallica&api_key=YOUR_API_KEY&format=json
	```

	```json
	{
		"similarartists": {
			"artist": [
				{
					"name": "Megadeth",
					"mbid": "a9044915-8be3-4c7e-b11f-9e2d2ea0a91e",
					"match": "1",
					"url": "https://www.last.fm/music/Megadeth",
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
					],
					"streamable": "0"
				},
				{
					"name": "Pantera",
					"mbid": "541f16f5-ad7a-428e-af89-9fa1b16d3c9c",
					"match": "0.600213",
					"url": "https://www.last.fm/music/Pantera",
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
					],
					"streamable": "0"
				},
				{
					"name": "Slayer",
					"mbid": "bdacc37b-8633-4bf8-9dd5-4662ee651aec",
					"match": "0.564283",
					"url": "https://www.last.fm/music/Slayer",
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
					],
					"streamable": "0"
				},
				... and 97 more
			],
			"@attr": {
				"artist": "Metallica"
			}
		}
	}
	```

??? warning "Example response of an artist/track that doesnt exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=artist.getSimilar&artist=artistthatdoesntexist&api_key=YOUR_API_KEY&format=json
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

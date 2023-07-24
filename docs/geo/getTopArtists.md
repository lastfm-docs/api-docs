Get the most popular artists on Last.fm by country.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `country` | [string][string] | `none` | :white_check_mark: | A country name, as defined by the ISO 3166-1 country names standard.
| `limit` | [number][number] | 50 | :negative_squared_cross_mark: | The number of results to fetch per page.
| `page` | [number][number] | 1 | :negative_squared_cross_mark: | The page number to fetch.
| `api_key` | [key][key] | `none` | :white_check_mark: | A Last.fm API key.

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
	| country   | Canada        |
	| limit     | 10            |
	| api_key   | YOUR_API_KEY  |
	| format    | json          |

	HTTP status: `200 OK`

	```
	https://ws.audioscrobbler.com/2.0/?method=geo.getTopArtists&country=Canada&limit=10&api_key=YOUR_API_KEY&format=json
	```
	```json
	{
		"topartists": {
			"artist": [
				{
					"name": "Radiohead",
					"listeners": "6075666",
					"mbid": "a74b1b7f-71a5-4011-9441-d0b5e4122711",
					"url": "https://www.last.fm/music/Radiohead",
					"streamable": "0",
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
						}
					]
				},
				{
					"name": "The Weeknd",
					"listeners": "3389182",
					"mbid": "c8b03190-306c-4120-bb0b-6f2ebfc06ea9",
					"url": "https://www.last.fm/music/The+Weeknd",
					"streamable": "0",
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
						}
					]
				},
				{
					"name": "David Bowie",
					"listeners": "4312121",
					"mbid": "5441c29d-3602-4898-b1a1-b77fa23b8e50",
					"url": "https://www.last.fm/music/David+Bowie",
					"streamable": "0",
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
						}
					]
				},
				{
					"name": "The Beatles",
					"listeners": "4923466",
					"mbid": "b10bbbfc-cf9e-42e0-be17-e2c3e1d2600d",
					"url": "https://www.last.fm/music/The+Beatles",
					"streamable": "0",
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
						}
					]
				},
				{
					"name": "Drake",
					"listeners": "5037233",
					"mbid": "b49b81cc-d5b7-4bdd-aadb-385df8de69a6",
					"url": "https://www.last.fm/music/Drake",
					"streamable": "0",
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
						}
					]
				},
				{
					"name": "Coldplay",
					"listeners": "6980934",
					"mbid": "cc197bad-dc9c-440d-a5b5-d52ba2e14234",
					"url": "https://www.last.fm/music/Coldplay",
					"streamable": "0",
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
						}
					]
				},
				{
					"name": "Kanye West",
					"listeners": "6097008",
					"mbid": "164f0d73-1234-4e2c-8743-d77bf2191051",
					"url": "https://www.last.fm/music/Kanye+West",
					"streamable": "0",
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
						}
					]
				},
				{
					"name": "Daft Punk",
					"listeners": "4899705",
					"mbid": "056e4f3e-d505-4dad-8ec1-d04f521cbb56",
					"url": "https://www.last.fm/music/Daft+Punk",
					"streamable": "0",
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
						}
					]
				},
				{
					"name": "Queen",
					"listeners": "5451558",
					"mbid": "420ca290-76c5-41af-999e-564d7c71f1a7",
					"url": "https://www.last.fm/music/Queen",
					"streamable": "0",
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
						}
					]
				},
				{
					"name": "Rihanna",
					"listeners": "6225146",
					"mbid": "db36a76f-4cdf-43ac-8cd0-5e48092d2bae",
					"url": "https://www.last.fm/music/Rihanna",
					"streamable": "0",
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
						}
					]
				}
			],
			"@attr": {
				"country": "Canada",
				"page": "1",
				"perPage": "10",
				"totalPages": "147425",
				"total": "1474249"
			}
		}
	}
	```

??? warning "Example response of a country that doesn't exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=geo.getTopArtists&country=Texas&limit=10&api_key=YOUR_API_KEY&format=json
    ```
		```json
		{
			"error": 6,
			"message": "country param invalid",
			"links": []
		}
		```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create

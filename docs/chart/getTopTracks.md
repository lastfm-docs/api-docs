Returns the top tracks chart.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
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

## Examples

??? note "Example response"

	| Parameter | Value         |
	| --------- | ------------- |
	| limit     | 10            |
	| api_key   | YOUR_API_KEY  |
	| format    | json          |

	HTTP status: `200 OK`

	```
	https://ws.audioscrobbler.com/2.0/?method=chart.getTopTracks&limit=10&api_key=YOUR_API_KEY&format=json
	```
	```json
	{
		"tracks": {
			"track": [
				{
					"name": "vampire",
					"duration": "0",
					"playcount": "5356360",
					"listeners": "417921",
					"mbid": "",
					"url": "https://www.last.fm/music/Olivia+Rodrigo/_/vampire",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Olivia Rodrigo",
						"mbid": "",
						"url": "https://www.last.fm/music/Olivia+Rodrigo"
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
						}
					]
				},
				{
					"name": "Cruel Summer",
					"duration": "0",
					"playcount": "20910268",
					"listeners": "760544",
					"mbid": "",
					"url": "https://www.last.fm/music/Taylor+Swift/_/Cruel+Summer",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Taylor Swift",
						"mbid": "20244d07-534f-4eff-b4d4-930878889970",
						"url": "https://www.last.fm/music/Taylor+Swift"
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
						}
					]
				},
				{
					"name": "Kill Bill",
					"duration": "0",
					"playcount": "19898201",
					"listeners": "1086519",
					"mbid": "",
					"url": "https://www.last.fm/music/SZA/_/Kill+Bill",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "SZA",
						"mbid": "272989c8-5535-492d-a25c-9f58803e027f",
						"url": "https://www.last.fm/music/SZA"
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
						}
					]
				},
				{
					"name": "See You Again (feat. Kali Uchis)",
					"duration": "0",
					"playcount": "19146518",
					"listeners": "1124028",
					"mbid": "",
					"url": "https://www.last.fm/music/Tyler,+the+Creator/_/See+You+Again+(feat.+Kali+Uchis)",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Tyler, the Creator",
						"mbid": "f6beac20-5dfe-4d1f-ae02-0b0a740aafd6",
						"url": "https://www.last.fm/music/Tyler,+the+Creator"
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
						}
					]
				},
				{
					"name": "Mine (Taylor's Version)",
					"duration": "0",
					"playcount": "1422670",
					"listeners": "302338",
					"mbid": "",
					"url": "https://www.last.fm/music/Taylor+Swift/_/Mine+(Taylor%27s+Version)",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Taylor Swift",
						"mbid": "20244d07-534f-4eff-b4d4-930878889970",
						"url": "https://www.last.fm/music/Taylor+Swift"
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
						}
					]
				},
				{
					"name": "Enchanted (Taylor's Version)",
					"duration": "0",
					"playcount": "1388852",
					"listeners": "300643",
					"mbid": "",
					"url": "https://www.last.fm/music/Taylor+Swift/_/Enchanted+(Taylor%27s+Version)",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Taylor Swift",
						"mbid": "20244d07-534f-4eff-b4d4-930878889970",
						"url": "https://www.last.fm/music/Taylor+Swift"
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
						}
					]
				},
				{
					"name": "Back To December (Taylor's Version)",
					"duration": "0",
					"playcount": "1430032",
					"listeners": "298251",
					"mbid": "",
					"url": "https://www.last.fm/music/Taylor+Swift/_/Back+To+December+(Taylor%27s+Version)",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Taylor Swift",
						"mbid": "20244d07-534f-4eff-b4d4-930878889970",
						"url": "https://www.last.fm/music/Taylor+Swift"
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
						}
					]
				},
				{
					"name": "I Can See You (Taylor’s Version) (From The Vault)",
					"duration": "0",
					"playcount": "2465365",
					"listeners": "281404",
					"mbid": "",
					"url": "https://www.last.fm/music/Taylor+Swift/_/I+Can+See+You+(Taylor%E2%80%99s+Version)+(From+The+Vault)",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Taylor Swift",
						"mbid": "20244d07-534f-4eff-b4d4-930878889970",
						"url": "https://www.last.fm/music/Taylor+Swift"
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
						}
					]
				},
				{
					"name": "Sparks Fly (Taylor’s Version)",
					"duration": "0",
					"playcount": "1212192",
					"listeners": "274862",
					"mbid": "",
					"url": "https://www.last.fm/music/Taylor+Swift/_/Sparks+Fly+(Taylor%E2%80%99s+Version)",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Taylor Swift",
						"mbid": "20244d07-534f-4eff-b4d4-930878889970",
						"url": "https://www.last.fm/music/Taylor+Swift"
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
						}
					]
				},
				{
					"name": "Better Than Revenge (Taylor's Version)",
					"duration": "0",
					"playcount": "1367524",
					"listeners": "274519",
					"mbid": "",
					"url": "https://www.last.fm/music/Taylor+Swift/_/Better+Than+Revenge+(Taylor%27s+Version)",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Taylor Swift",
						"mbid": "20244d07-534f-4eff-b4d4-930878889970",
						"url": "https://www.last.fm/music/Taylor+Swift"
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
						}
					]
				}
			],
			"@attr": {
				"page": "1",
				"perPage": "10",
				"totalPages": "3503455",
				"total": "35034547"
			}
		}
	}
	```

[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create

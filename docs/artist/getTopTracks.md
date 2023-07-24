Get the top tracks by an artist on Last.fm, ordered by popularity.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `artist` | [string][string] | `none` | :white_check_mark: \* | The artist name to fetch information for.
| `mbid` | [string][string] | `none` | :negative_squared_cross_mark: | The artist's MusicBrainz ID.
| `autocorrect` | [number][number] | 0 | :negative_squared_cross_mark: | Transform misspelled artist names into correct artist names, returning the correct version instead. The corrected artist name will be returned in the response.
| `limit` | [number][number] | 50 | :negative_squared_cross_mark: | The number of results to fetch per page.
| `page` | [number][number] | 1 | :negative_squared_cross_mark: | The page number to fetch.
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
	| artist    | Chris Cornell |
	| api_key   | YOUR_API_KEY  |
	| format    | json          |

	HTTP status: `200 OK`

	```
	https://ws.audioscrobbler.com/2.0/?method=artist.getTopTracks&artist=Chris Cornell&api_key=YOUR_API_KEY&format=json
	```
	```json
	{
		"toptracks": {
			"track": [
				{
					"name": "You Know My Name",
					"playcount": "2053916",
					"listeners": "335135",
					"mbid": "609737d4-a062-4752-a38d-20576924fa56",
					"url": "https://www.last.fm/music/Chris+Cornell/_/You+Know+My+Name",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "1"
					}
				},
				{
					"name": "Billie Jean",
					"playcount": "750719",
					"listeners": "181586",
					"mbid": "30ebdc92-897f-41fb-b533-98964e448270",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Billie+Jean",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "2"
					}
				},
				{
					"name": "Can't Change Me",
					"playcount": "751720",
					"listeners": "175489",
					"mbid": "75a38520-5b93-4154-8148-44f619d27227",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Can%27t+Change+Me",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "3"
					}
				},
				{
					"name": "Arms Around Your Love",
					"playcount": "400232",
					"listeners": "105501",
					"mbid": "ddbd6223-c252-4a06-9626-469d8a275372",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Arms+Around+Your+Love",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "4"
					}
				},
				{
					"name": "You Know My Name - From \"Casino Royale\" Soundtrack",
					"playcount": "584609",
					"listeners": "99115",
					"url": "https://www.last.fm/music/Chris+Cornell/_/You+Know+My+Name+-+From+%22Casino+Royale%22+Soundtrack",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "5"
					}
				},
				{
					"name": "Nearly Forgot My Broken Heart",
					"playcount": "535398",
					"listeners": "96734",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Nearly+Forgot+My+Broken+Heart",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "6"
					}
				},
				{
					"name": "Seasons",
					"playcount": "422331",
					"listeners": "95065",
					"mbid": "b62dd32d-d6f8-49eb-9fe4-ca90591dcaa0",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Seasons",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "7"
					}
				},
				{
					"name": "No Such Thing",
					"playcount": "280051",
					"listeners": "85997",
					"mbid": "842809ed-b313-4dee-8e34-6f22b5806e2a",
					"url": "https://www.last.fm/music/Chris+Cornell/_/No+Such+Thing",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "8"
					}
				},
				{
					"name": "Preaching The End Of The World",
					"playcount": "325059",
					"listeners": "79084",
					"mbid": "af19bb10-d6b9-49c9-8438-1a9f74acded9",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Preaching+The+End+Of+The+World",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "9"
					}
				},
				{
					"name": "Part Of Me",
					"playcount": "395427",
					"listeners": "78001",
					"mbid": "302c7d29-ed8a-4805-a2de-f9921698ddb6",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Part+Of+Me",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "10"
					}
				},
				{
					"name": "She'll Never Be Your Man",
					"playcount": "216534",
					"listeners": "72132",
					"mbid": "0f27320f-b565-4684-8b6f-b89a105586c8",
					"url": "https://www.last.fm/music/Chris+Cornell/_/She%27ll+Never+Be+Your+Man",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "11"
					}
				},
				{
					"name": "Scream",
					"playcount": "370350",
					"listeners": "70723",
					"mbid": "37675aed-c453-4161-8bc3-adbd3304acf2",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Scream",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "12"
					}
				},
				{
					"name": "Wave Goodbye",
					"playcount": "253637",
					"listeners": "69768",
					"mbid": "5873a41f-b7f2-49e0-b152-99e49363ecbf",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Wave+Goodbye",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "13"
					}
				},
				{
					"name": "Flutter Girl",
					"playcount": "250995",
					"listeners": "69537",
					"mbid": "92fedcf0-63b8-4404-8afd-bcca71099edd",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Flutter+Girl",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "14"
					}
				},
				{
					"name": "Poison Eye",
					"playcount": "189950",
					"listeners": "63613",
					"mbid": "4be9e3e6-8f6a-4022-b044-f081ef765c9f",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Poison+Eye",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "15"
					}
				},
				{
					"name": "When I'm Down",
					"playcount": "256511",
					"listeners": "63161",
					"mbid": "b536df4d-6ef4-4a28-9d38-ebb3f6c3d83f",
					"url": "https://www.last.fm/music/Chris+Cornell/_/When+I%27m+Down",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "16"
					}
				},
				{
					"name": "Patience",
					"playcount": "274997",
					"listeners": "62307",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Patience",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "17"
					}
				},
				{
					"name": "Scar On The Sky",
					"playcount": "207525",
					"listeners": "61158",
					"mbid": "cd4fde2d-4c95-4fdd-bb73-375559307c3c",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Scar+On+The+Sky",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "18"
					}
				},
				{
					"name": "Follow My Way",
					"playcount": "239901",
					"listeners": "60723",
					"mbid": "ef7ab754-3c2a-4d4c-9c74-a467aec37d2a",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Follow+My+Way",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "19"
					}
				},
				{
					"name": "Sweet Euphoria",
					"playcount": "231561",
					"listeners": "59765",
					"mbid": "4e09d99a-3ca8-4b07-8287-09570ed3ae9f",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Sweet+Euphoria",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "20"
					}
				},
				{
					"name": "Safe and Sound",
					"playcount": "184790",
					"listeners": "59383",
					"mbid": "ef002f96-7b51-4768-9db1-192bec43a6ca",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Safe+and+Sound",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "21"
					}
				},
				{
					"name": "Ghosts",
					"playcount": "182642",
					"listeners": "59190",
					"mbid": "81b5ed32-d711-470e-8ceb-14345af33038",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Ghosts",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "22"
					}
				},
				{
					"name": "Moonchild",
					"playcount": "207872",
					"listeners": "55205",
					"mbid": "17b89b06-2731-4747-acf9-8d53b889b26a",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Moonchild",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "23"
					}
				},
				{
					"name": "Pillow Of Your Bones",
					"playcount": "214473",
					"listeners": "54340",
					"mbid": "4f71158c-0c69-4369-91c5-c77f9fc29d1a",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Pillow+Of+Your+Bones",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "24"
					}
				},
				{
					"name": "Killing Birds",
					"playcount": "173002",
					"listeners": "53809",
					"mbid": "eb127009-7dad-4863-85c9-6bb1039e59c4",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Killing+Birds",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "25"
					}
				},
				{
					"name": "Steel Rain",
					"playcount": "202074",
					"listeners": "52212",
					"mbid": "d79e9dd9-78c8-443a-9eb8-42a449895f66",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Steel+Rain",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "26"
					}
				},
				{
					"name": "Your Soul Today",
					"playcount": "159482",
					"listeners": "51248",
					"mbid": "2acfd9df-fc4a-4aa2-8fbc-5aed92c1f718",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Your+Soul+Today",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "27"
					}
				},
				{
					"name": "Disappearing One",
					"playcount": "194944",
					"listeners": "51231",
					"mbid": "849e18bb-9915-46aa-84a7-be75d08e6f74",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Disappearing+One",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "28"
					}
				},
				{
					"name": "Mission",
					"playcount": "177156",
					"listeners": "51135",
					"mbid": "929dc1c5-57e7-4395-bc2b-f9e122ffd23a",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Mission",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "29"
					}
				},
				{
					"name": "Finally Forever",
					"playcount": "160108",
					"listeners": "50438",
					"mbid": "273549c1-df0e-44e7-b8da-e589f536f441",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Finally+Forever",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "30"
					}
				},
				{
					"name": "Black Hole Sun - Recorded Live At Red Robinson Show Theatre, Vancouver, Canada on April 30, 2011",
					"playcount": "175460",
					"listeners": "48467",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Black+Hole+Sun+-+Recorded+Live+At+Red+Robinson+Show+Theatre,+Vancouver,+Canada+on+April+30,+2011",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "31"
					}
				},
				{
					"name": "Disappearing Act",
					"playcount": "143811",
					"listeners": "45155",
					"mbid": "5fa5a433-144f-4a93-b3a9-6d5b481c0b88",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Disappearing+Act",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "32"
					}
				},
				{
					"name": "Sunshower",
					"playcount": "171810",
					"listeners": "44207",
					"mbid": "d38a4f03-eb9f-4465-afbe-578dd89819c6",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Sunshower",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "33"
					}
				},
				{
					"name": "Silence The Voices",
					"playcount": "135627",
					"listeners": "44017",
					"mbid": "4c43284e-027b-44da-a649-8a47f9a735be",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Silence+The+Voices",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "34"
					}
				},
				{
					"name": "Ground Zero",
					"playcount": "163895",
					"listeners": "42878",
					"mbid": "3f88604a-145d-4c2a-9ab9-066f31900781",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Ground+Zero",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "35"
					}
				},
				{
					"name": "Nothing Compares 2 U - Live at SiriusXM/2015",
					"playcount": "189154",
					"listeners": "39344",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Nothing+Compares+2+U+-+Live+at+SiriusXM%2F2015",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "36"
					}
				},
				{
					"name": "Time",
					"playcount": "147291",
					"listeners": "38874",
					"mbid": "5d6ff023-0b51-46f9-9fa8-44858b7cfe6f",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Time",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "37"
					}
				},
				{
					"name": "Long Gone",
					"playcount": "166320",
					"listeners": "36104",
					"mbid": "b8ce7f02-7245-4662-ba77-df0631c7bbd6",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Long+Gone",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "38"
					}
				},
				{
					"name": "Never Far Away",
					"playcount": "140661",
					"listeners": "34554",
					"mbid": "f1c72c1d-6ef7-416d-beee-7e6ff9006bcc",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Never+Far+Away",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "39"
					}
				},
				{
					"name": "You Know My Name - From Casino Royale",
					"playcount": "110326",
					"listeners": "33784",
					"url": "https://www.last.fm/music/Chris+Cornell/_/You+Know+My+Name+-+From+Casino+Royale",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "40"
					}
				},
				{
					"name": "Sweet Revenge",
					"playcount": "122289",
					"listeners": "32222",
					"mbid": "18e5167b-77af-4ad2-8540-8f2d4f0d3b83",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Sweet+Revenge",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "41"
					}
				},
				{
					"name": "Get Up",
					"playcount": "119339",
					"listeners": "31232",
					"mbid": "b13bfc94-5955-4e7f-8278-3421d4635cf4",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Get+Up",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "42"
					}
				},
				{
					"name": "Like A Stone - Recorded Live At Queen Elizabeth Theatre, Toronto, ON on April 20, 2011",
					"playcount": "130078",
					"listeners": "31106",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Like+A+Stone+-+Recorded+Live+At+Queen+Elizabeth+Theatre,+Toronto,+ON+on+April+20,+2011",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "43"
					}
				},
				{
					"name": "Climbing Up The Walls",
					"playcount": "152921",
					"listeners": "31037",
					"mbid": "7b128208-8cc3-4793-8bff-6acac95c5c1e",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Climbing+Up+The+Walls",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "44"
					}
				},
				{
					"name": "The Promise",
					"playcount": "118253",
					"listeners": "30728",
					"url": "https://www.last.fm/music/Chris+Cornell/_/The+Promise",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "45"
					}
				},
				{
					"name": "Before We Disappear",
					"playcount": "136213",
					"listeners": "29330",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Before+We+Disappear",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "46"
					}
				},
				{
					"name": "Enemy",
					"playcount": "126688",
					"listeners": "28479",
					"mbid": "a26754ad-cd62-463a-b2a3-b132d3f62e39",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Enemy",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "47"
					}
				},
				{
					"name": "Today",
					"playcount": "102141",
					"listeners": "28121",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Today",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "48"
					}
				},
				{
					"name": "Take Me Alive",
					"playcount": "109268",
					"listeners": "27769",
					"mbid": "753ee778-bce3-464e-bb3a-b84b1a98a710",
					"url": "https://www.last.fm/music/Chris+Cornell/_/Take+Me+Alive",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "49"
					}
				},
				{
					"name": "When Bad Does Good",
					"playcount": "89776",
					"listeners": "26583",
					"url": "https://www.last.fm/music/Chris+Cornell/_/When+Bad+Does+Good",
					"streamable": "0",
					"artist": {
						"name": "Chris Cornell",
						"mbid": "cbf9738d-8f81-4a92-bc64-ede09341652d",
						"url": "https://www.last.fm/music/Chris+Cornell"
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
					],
					"@attr": {
						"rank": "50"
					}
				}
			],
			"@attr": {
				"artist": "Chris Cornell",
				"page": "1",
				"perPage": "50",
				"totalPages": "429",
				"total": "21406"
			}
		}
	}
	```

??? warning "Example response of an artist/track that doesnt exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=artist.getTopTracks&artist=artistthatdoesntexist&api_key=YOUR_API_KEY&format=json
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

Get the most popular tracks on Last.fm by country

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `country` | [string][string] | `none` | :white_check_mark: | A country name, as defined by the ISO 3166-1 country names standard.
| `location` | [string][string] | `none` | :negative_squared_cross_mark: | A metro name, to fetch the charts for (must be within the country specified)
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
	https://ws.audioscrobbler.com/2.0/?method=geo.getTopTracks&country=Canada&limit=10&api_key=YOUR_API_KEY&format=json
	```
	```json
	{
		"tracks": {
			"track": [
				{
					"name": "Mr. Brightside",
					"duration": "224",
					"listeners": "2764662",
					"mbid": "37d516ab-d61f-4bcb-9316-7a0b3eb845a8",
					"url": "https://www.last.fm/music/The+Killers/_/Mr.+Brightside",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "The Killers",
						"mbid": "95e1ead9-4d31-4808-a7ac-32c3614c116b",
						"url": "https://www.last.fm/music/The+Killers"
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
						"rank": "0"
					}
				},
				{
					"name": "Smells Like Teen Spirit",
					"duration": "301",
					"listeners": "2913753",
					"mbid": "0ebe2d92-a11d-4b2b-9922-806383074ed7",
					"url": "https://www.last.fm/music/Nirvana/_/Smells+Like+Teen+Spirit",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Nirvana",
						"mbid": "9282c8b4-ca0b-4c6b-b7e3-4f7762dfc4d6",
						"url": "https://www.last.fm/music/Nirvana"
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
					"name": "Can't Feel My Face",
					"duration": "0",
					"listeners": "1071711",
					"mbid": "",
					"url": "https://www.last.fm/music/The+Weeknd/_/Can%27t+Feel+My+Face",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "The Weeknd",
						"mbid": "c8b03190-306c-4120-bb0b-6f2ebfc06ea9",
						"url": "https://www.last.fm/music/The+Weeknd"
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
					"name": "Seven Nation Army",
					"duration": "449",
					"listeners": "2096870",
					"mbid": "24cc8311-98fd-423a-bed1-97728f5eabc5",
					"url": "https://www.last.fm/music/The+White+Stripes/_/Seven+Nation+Army",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "The White Stripes",
						"mbid": "11ae9fbb-f3d7-4a47-936f-4c0a04d3b3b5",
						"url": "https://www.last.fm/music/The+White+Stripes"
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
					"name": "The Less I Know the Better",
					"duration": "0",
					"listeners": "1448851",
					"mbid": "",
					"url": "https://www.last.fm/music/Tame+Impala/_/The+Less+I+Know+the+Better",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Tame Impala",
						"mbid": "63aa26c3-d59b-4da4-84ac-716b54f1ef4d",
						"url": "https://www.last.fm/music/Tame+Impala"
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
					"name": "Karma Police",
					"duration": "0",
					"listeners": "2191927",
					"mbid": "0790ba6c-e0b1-4891-b82f-b4db9a5a927f",
					"url": "https://www.last.fm/music/Radiohead/_/Karma+Police",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Radiohead",
						"mbid": "a74b1b7f-71a5-4011-9441-d0b5e4122711",
						"url": "https://www.last.fm/music/Radiohead"
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
					"name": "Creep",
					"duration": "239",
					"listeners": "2485207",
					"mbid": "d11fcceb-dfc5-4d19-b45d-f4e8f6d3eaa6",
					"url": "https://www.last.fm/music/Radiohead/_/Creep",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Radiohead",
						"mbid": "a74b1b7f-71a5-4011-9441-d0b5e4122711",
						"url": "https://www.last.fm/music/Radiohead"
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
					"name": "Come as You Are",
					"duration": "208",
					"listeners": "2552473",
					"mbid": "e05035a3-14ac-4f88-a160-0a144530004e",
					"url": "https://www.last.fm/music/Nirvana/_/Come+as+You+Are",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Nirvana",
						"mbid": "9282c8b4-ca0b-4c6b-b7e3-4f7762dfc4d6",
						"url": "https://www.last.fm/music/Nirvana"
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
					"name": "Feel Good Inc.",
					"duration": "221",
					"listeners": "2353558",
					"mbid": "5660558a-bfa7-416f-99d9-a34ca0a34515",
					"url": "https://www.last.fm/music/Gorillaz/_/Feel+Good+Inc.",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Gorillaz",
						"mbid": "e21857d5-3256-4547-afb3-4b6ded592596",
						"url": "https://www.last.fm/music/Gorillaz"
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
					"name": "Africa",
					"duration": "236",
					"listeners": "1463507",
					"mbid": "d0b884c8-6100-4ca2-855f-5ef27d963807",
					"url": "https://www.last.fm/music/Toto/_/Africa",
					"streamable": {
						"#text": "0",
						"fulltrack": "0"
					},
					"artist": {
						"name": "Toto",
						"mbid": "aab5c954-cabe-432e-899e-1c4f99757327",
						"url": "https://www.last.fm/music/Toto"
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
				}
			],
			"@attr": {
				"country": "Canada",
				"page": "1",
				"perPage": "10",
				"totalPages": "1195347",
				"total": "11953466"
			}
		}
	}
	```

??? warning "Example response of a country that doesn't exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=geo.getTopTracks&country=Texas&limit=10&api_key=YOUR_API_KEY&format=json
    ```
    ```json
		{
			"error": 6,
			"message": "country param required",
			"links": []
		}
    ```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create

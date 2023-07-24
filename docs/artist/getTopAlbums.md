Get the top albums for an artist on Last.fm, ordered by popularity.

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
	| artist    | Soundgarden   |
	| api_key   | YOUR_API_KEY  |
	| format    | json          |

	HTTP status: `200 OK`

	```
	https://ws.audioscrobbler.com/2.0/?method=artist.getTopAlbums&artist=Soundgarden&api_key=YOUR_API_KEY&format=json
	```

	```json
	{
		"topalbums": {
			"album": [
				{
					"name": "Superunknown",
					"playcount": 16024346,
					"mbid": "9d005b9c-fd45-412c-970b-3e64a59f84cd",
					"url": "https://www.last.fm/music/Soundgarden/Superunknown",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/850494d70ef94137bb5b50b267fbe487.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/850494d70ef94137bb5b50b267fbe487.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/850494d70ef94137bb5b50b267fbe487.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/850494d70ef94137bb5b50b267fbe487.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Superunknown (Deluxe Edition)",
					"playcount": 6193259,
					"url": "https://www.last.fm/music/Soundgarden/Superunknown+(Deluxe+Edition)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/89e3a9e707ee928602f8341206407d99.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/89e3a9e707ee928602f8341206407d99.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/89e3a9e707ee928602f8341206407d99.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/89e3a9e707ee928602f8341206407d99.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Down on the Upside",
					"playcount": 7238720,
					"mbid": "3475c257-246f-36f4-88f4-196dbf7bbed1",
					"url": "https://www.last.fm/music/Soundgarden/Down+on+the+Upside",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/ba37e6fabc3f445280187c99a024de99.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/ba37e6fabc3f445280187c99a024de99.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/ba37e6fabc3f445280187c99a024de99.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/ba37e6fabc3f445280187c99a024de99.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Badmotorfinger",
					"playcount": 6451509,
					"mbid": "38153879-cf9e-39a0-a7f6-8a2d34a3d209",
					"url": "https://www.last.fm/music/Soundgarden/Badmotorfinger",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/935169b2a7744529b7a905cc07e31bb7.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/935169b2a7744529b7a905cc07e31bb7.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/935169b2a7744529b7a905cc07e31bb7.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/935169b2a7744529b7a905cc07e31bb7.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Superunknown (20th Anniversary)",
					"playcount": 4589599,
					"url": "https://www.last.fm/music/Soundgarden/Superunknown+(20th+Anniversary)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/1397dc507209cbdbe5b8575fbafa9878.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/1397dc507209cbdbe5b8575fbafa9878.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/1397dc507209cbdbe5b8575fbafa9878.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/1397dc507209cbdbe5b8575fbafa9878.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Badmotorfinger (25th Anniversary Remaster)",
					"playcount": 2187826,
					"url": "https://www.last.fm/music/Soundgarden/Badmotorfinger+(25th+Anniversary+Remaster)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/4e349cc63f6ea0bf42ba7dab83c82d48.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/4e349cc63f6ea0bf42ba7dab83c82d48.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/4e349cc63f6ea0bf42ba7dab83c82d48.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/4e349cc63f6ea0bf42ba7dab83c82d48.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Telephantasm",
					"playcount": 1149521,
					"mbid": "0653ea23-f0e6-4708-b090-d9afcb4ed7c2",
					"url": "https://www.last.fm/music/Soundgarden/Telephantasm",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/4a6e03d6baf0b969889009dcbe6f16a5.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/4a6e03d6baf0b969889009dcbe6f16a5.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/4a6e03d6baf0b969889009dcbe6f16a5.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/4a6e03d6baf0b969889009dcbe6f16a5.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "A-Sides",
					"playcount": 2430098,
					"mbid": "a1384642-7aa5-4f3a-9839-5e7ad4ab0f23",
					"url": "https://www.last.fm/music/Soundgarden/A-Sides",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/0b4a78e2aa35fac124ed2e20a0d5cd54.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/0b4a78e2aa35fac124ed2e20a0d5cd54.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/0b4a78e2aa35fac124ed2e20a0d5cd54.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/0b4a78e2aa35fac124ed2e20a0d5cd54.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Louder Than Love",
					"playcount": 2312435,
					"mbid": "7adf8ad6-e72c-42c6-896a-9636e3d25fef",
					"url": "https://www.last.fm/music/Soundgarden/Louder+Than+Love",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/3efe7734ad166f95afb829a297e82573.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/3efe7734ad166f95afb829a297e82573.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/3efe7734ad166f95afb829a297e82573.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/3efe7734ad166f95afb829a297e82573.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "King Animal",
					"playcount": 2379135,
					"mbid": "e72ffed5-b310-4f55-8d3b-904172e46402",
					"url": "https://www.last.fm/music/Soundgarden/King+Animal",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/d3553672826d4e72b61fdd89d9478276.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/d3553672826d4e72b61fdd89d9478276.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/d3553672826d4e72b61fdd89d9478276.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/d3553672826d4e72b61fdd89d9478276.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Ultramega OK",
					"playcount": 1451225,
					"mbid": "b7ef61ea-231c-33d8-a996-1efda7e37659",
					"url": "https://www.last.fm/music/Soundgarden/Ultramega+OK",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/d8a7a2aa60890ae1bfcaba4f31f9600b.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/d8a7a2aa60890ae1bfcaba4f31f9600b.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/d8a7a2aa60890ae1bfcaba4f31f9600b.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/d8a7a2aa60890ae1bfcaba4f31f9600b.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Telephantasm (Deluxe Edition)",
					"playcount": 532564,
					"url": "https://www.last.fm/music/Soundgarden/Telephantasm+(Deluxe+Edition)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/c2740dda8d274e0291462183b5fdc439.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/c2740dda8d274e0291462183b5fdc439.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/c2740dda8d274e0291462183b5fdc439.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/c2740dda8d274e0291462183b5fdc439.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Screaming Life/Fopp",
					"playcount": 473166,
					"mbid": "144002c8-8d56-497d-9a12-08be190f7637",
					"url": "https://www.last.fm/music/Soundgarden/Screaming+Life%2FFopp",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/2ed3bc9192013fcda8b2cfa9008b9cdf.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/2ed3bc9192013fcda8b2cfa9008b9cdf.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/2ed3bc9192013fcda8b2cfa9008b9cdf.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2ed3bc9192013fcda8b2cfa9008b9cdf.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Avengers Assemble",
					"playcount": 186735,
					"url": "https://www.last.fm/music/Soundgarden/Avengers+Assemble",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/975b0345831347bf88647182a445ddd0.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/975b0345831347bf88647182a445ddd0.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/975b0345831347bf88647182a445ddd0.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/975b0345831347bf88647182a445ddd0.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Superunknown (Super Deluxe)",
					"playcount": 495265,
					"url": "https://www.last.fm/music/Soundgarden/Superunknown+(Super+Deluxe)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/3d19ef5be6db4e44ce8869e321e3b971.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/3d19ef5be6db4e44ce8869e321e3b971.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/3d19ef5be6db4e44ce8869e321e3b971.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/3d19ef5be6db4e44ce8869e321e3b971.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Ultramega OK (Expanded Reissue)",
					"playcount": 403726,
					"url": "https://www.last.fm/music/Soundgarden/Ultramega+OK+(Expanded+Reissue)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/72887a31e492b237fc7324b8861db95d.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/72887a31e492b237fc7324b8861db95d.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/72887a31e492b237fc7324b8861db95d.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/72887a31e492b237fc7324b8861db95d.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Echo Of Miles: Scattered Tracks Across The Path",
					"playcount": 342224,
					"mbid": "5d213faa-d22c-4fd5-95f9-c74a7a24a38b",
					"url": "https://www.last.fm/music/Soundgarden/Echo+Of+Miles:+Scattered+Tracks+Across+The+Path",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/c5c14f0f8fb7cc817cc3220f3e33e23d.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/c5c14f0f8fb7cc817cc3220f3e33e23d.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/c5c14f0f8fb7cc817cc3220f3e33e23d.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/c5c14f0f8fb7cc817cc3220f3e33e23d.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "(null)",
					"playcount": 345416,
					"url": "https://www.last.fm/music/Soundgarden/(null)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "",
							"size": "small"
						},
						{
							"#text": "",
							"size": "medium"
						},
						{
							"#text": "",
							"size": "large"
						},
						{
							"#text": "",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Live On I-5",
					"playcount": 327687,
					"mbid": "9ea14f4b-451c-3ee7-9b7a-1d06876c884d",
					"url": "https://www.last.fm/music/Soundgarden/Live+On+I-5",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/3bde6f036f4247f59b6c5b4ffcab52d6.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/3bde6f036f4247f59b6c5b4ffcab52d6.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/3bde6f036f4247f59b6c5b4ffcab52d6.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/3bde6f036f4247f59b6c5b4ffcab52d6.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Indie Anthems",
					"playcount": 102694,
					"url": "https://www.last.fm/music/Soundgarden/Indie+Anthems",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/a7b1d284483bac4d729af90c78365390.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/a7b1d284483bac4d729af90c78365390.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/a7b1d284483bac4d729af90c78365390.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/a7b1d284483bac4d729af90c78365390.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "King Animal (Deluxe Version)",
					"playcount": 357343,
					"url": "https://www.last.fm/music/Soundgarden/King+Animal+(Deluxe+Version)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/6ccf05627fc43ad0bae58310980c80ff.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/6ccf05627fc43ad0bae58310980c80ff.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/6ccf05627fc43ad0bae58310980c80ff.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/6ccf05627fc43ad0bae58310980c80ff.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Badmotorfinger (Super Deluxe Edition)",
					"playcount": 249712,
					"url": "https://www.last.fm/music/Soundgarden/Badmotorfinger+(Super+Deluxe+Edition)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/2c1ccbab16279b39217a443695a4c160.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/2c1ccbab16279b39217a443695a4c160.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/2c1ccbab16279b39217a443695a4c160.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2c1ccbab16279b39217a443695a4c160.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Live to Rise",
					"playcount": 92297,
					"mbid": "e73ee206-754c-4b64-b173-39c7d168dfbe",
					"url": "https://www.last.fm/music/Soundgarden/Live+to+Rise",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/73f93f6a5d004055b954c392a28165ad.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/73f93f6a5d004055b954c392a28165ad.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/73f93f6a5d004055b954c392a28165ad.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/73f93f6a5d004055b954c392a28165ad.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Screaming Life / Fopp",
					"playcount": 321990,
					"url": "https://www.last.fm/music/Soundgarden/Screaming+Life+%2F+Fopp",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/d74020952b59a0eff4726d83a4cff480.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/d74020952b59a0eff4726d83a4cff480.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/d74020952b59a0eff4726d83a4cff480.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/d74020952b59a0eff4726d83a4cff480.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Dry As A Bone/Rehab Doll",
					"playcount": 49033,
					"url": "https://www.last.fm/music/Soundgarden/Dry+As+A+Bone%2FRehab+Doll",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/ea6b4208531dd1cb792500da0291c180.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/ea6b4208531dd1cb792500da0291c180.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/ea6b4208531dd1cb792500da0291c180.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/ea6b4208531dd1cb792500da0291c180.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Black Rain",
					"playcount": 62032,
					"mbid": "764e728f-89eb-4e58-9801-e35638fc4296",
					"url": "https://www.last.fm/music/Soundgarden/Black+Rain",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/cc4d8bc169eda5bb208ee19491e1b5fe.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/cc4d8bc169eda5bb208ee19491e1b5fe.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/cc4d8bc169eda5bb208ee19491e1b5fe.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/cc4d8bc169eda5bb208ee19491e1b5fe.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Fresh Deadly Rarities",
					"playcount": 102754,
					"mbid": "f8b8d76d-4701-48ff-bb8d-f7313e8e027d",
					"url": "https://www.last.fm/music/Soundgarden/Fresh+Deadly+Rarities",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/5954a60389054fbd9ac01f3df02d527d.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/5954a60389054fbd9ac01f3df02d527d.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/5954a60389054fbd9ac01f3df02d527d.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/5954a60389054fbd9ac01f3df02d527d.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Songs From The Superunknown",
					"playcount": 86720,
					"mbid": "db93d87d-2ee9-40af-a62a-1c438cac8c00",
					"url": "https://www.last.fm/music/Soundgarden/Songs+From+The+Superunknown",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/bedbbe29a9e1407e8f81e9313cd54ca0.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/bedbbe29a9e1407e8f81e9313cd54ca0.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/bedbbe29a9e1407e8f81e9313cd54ca0.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/bedbbe29a9e1407e8f81e9313cd54ca0.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Live from the Artists Den",
					"playcount": 135987,
					"url": "https://www.last.fm/music/Soundgarden/Live+from+the+Artists+Den",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/6cceaf198d358309dba76378a991d218.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/6cceaf198d358309dba76378a991d218.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/6cceaf198d358309dba76378a991d218.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/6cceaf198d358309dba76378a991d218.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Been Away Too Long",
					"playcount": 27130,
					"mbid": "f1efc0d8-06af-49cb-a8b8-5bec58dc6224",
					"url": "https://www.last.fm/music/Soundgarden/Been+Away+Too+Long",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/401ec622668d4ae8be6bca5cd40d6702.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/401ec622668d4ae8be6bca5cd40d6702.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/401ec622668d4ae8be6bca5cd40d6702.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/401ec622668d4ae8be6bca5cd40d6702.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "A-Sides (Best of)",
					"playcount": 199956,
					"url": "https://www.last.fm/music/Soundgarden/A-Sides+(Best+of)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/cc7b3a4eec1a4a6685c5954f256ac358.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/cc7b3a4eec1a4a6685c5954f256ac358.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/cc7b3a4eec1a4a6685c5954f256ac358.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/cc7b3a4eec1a4a6685c5954f256ac358.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Singles",
					"playcount": 21738,
					"url": "https://www.last.fm/music/Soundgarden/Singles",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/0af4ab6cff1e270fbc92bdf69be423a2.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/0af4ab6cff1e270fbc92bdf69be423a2.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/0af4ab6cff1e270fbc92bdf69be423a2.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/0af4ab6cff1e270fbc92bdf69be423a2.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Moonlight on Vermont",
					"playcount": 15543,
					"mbid": "ea7f9e57-3d15-45ff-9561-f6f993b44b86",
					"url": "https://www.last.fm/music/Soundgarden/Moonlight+on+Vermont",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/32e0aa644f504fb396dc53eb14a032d6.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/32e0aa644f504fb396dc53eb14a032d6.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/32e0aa644f504fb396dc53eb14a032d6.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/32e0aa644f504fb396dc53eb14a032d6.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Spoonman (Remix By Steve Aoki)",
					"playcount": 17347,
					"url": "https://www.last.fm/music/Soundgarden/Spoonman+(Remix+By+Steve+Aoki)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/7601cf1f2f464de09a7aa38673dc44f8.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/7601cf1f2f464de09a7aa38673dc44f8.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/7601cf1f2f464de09a7aa38673dc44f8.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/7601cf1f2f464de09a7aa38673dc44f8.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Flower",
					"playcount": 18395,
					"mbid": "b0cb89af-837c-4cdb-847f-384b5bf81a3a",
					"url": "https://www.last.fm/music/Soundgarden/Flower",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/a5974cde6f5945d1a81b0804378b60b3.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/a5974cde6f5945d1a81b0804378b60b3.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/a5974cde6f5945d1a81b0804378b60b3.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/a5974cde6f5945d1a81b0804378b60b3.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Storm",
					"playcount": 11641,
					"mbid": "d77e5cdb-08b2-40ac-b858-78b036e7520d",
					"url": "https://www.last.fm/music/Soundgarden/Storm",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/6a95393402a14b1ccb174123cc299561.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/6a95393402a14b1ccb174123cc299561.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/6a95393402a14b1ccb174123cc299561.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/6a95393402a14b1ccb174123cc299561.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Commentary",
					"playcount": 42947,
					"url": "https://www.last.fm/music/Soundgarden/Commentary",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/3d101e884298422ba07703df06ebf23b.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/3d101e884298422ba07703df06ebf23b.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/3d101e884298422ba07703df06ebf23b.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/3d101e884298422ba07703df06ebf23b.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Chris Cornell",
					"playcount": 24069,
					"url": "https://www.last.fm/music/Soundgarden/Chris+Cornell",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/c160c6b2bd0318b08aec60737c7d7af4.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/c160c6b2bd0318b08aec60737c7d7af4.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/c160c6b2bd0318b08aec60737c7d7af4.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/c160c6b2bd0318b08aec60737c7d7af4.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "True Romance",
					"playcount": 8855,
					"url": "https://www.last.fm/music/Soundgarden/True+Romance",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/c928d9f15d904100aa8e637a286a63f0.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/c928d9f15d904100aa8e637a286a63f0.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/c928d9f15d904100aa8e637a286a63f0.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/c928d9f15d904100aa8e637a286a63f0.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Singles - Original Motion Picture Soundtrack",
					"playcount": 9599,
					"url": "https://www.last.fm/music/Soundgarden/Singles+-+Original+Motion+Picture+Soundtrack",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/ccc5295a5de045b398878b3b26c29c55.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/ccc5295a5de045b398878b3b26c29c55.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/ccc5295a5de045b398878b3b26c29c55.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/ccc5295a5de045b398878b3b26c29c55.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Bad Motorfinger",
					"playcount": 25783,
					"url": "https://www.last.fm/music/Soundgarden/Bad+Motorfinger",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/3aef5778f987c4e7271b32a9392e453b.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/3aef5778f987c4e7271b32a9392e453b.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/3aef5778f987c4e7271b32a9392e453b.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/3aef5778f987c4e7271b32a9392e453b.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "True Power-Ballads / 3CD set",
					"playcount": 12214,
					"url": "https://www.last.fm/music/Soundgarden/True+Power-Ballads+%2F+3CD+set",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/22a98fab589d4d51ae5424d981f1cdbb.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/22a98fab589d4d51ae5424d981f1cdbb.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/22a98fab589d4d51ae5424d981f1cdbb.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/22a98fab589d4d51ae5424d981f1cdbb.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Echo Of Miles: The Originals",
					"playcount": 45254,
					"mbid": "6336fa07-73c8-4fda-af00-8494af76415e",
					"url": "https://www.last.fm/music/Soundgarden/Echo+Of+Miles:+The+Originals",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/3933222e11554537c5d0a50cf8d5d31d.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/3933222e11554537c5d0a50cf8d5d31d.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/3933222e11554537c5d0a50cf8d5d31d.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/3933222e11554537c5d0a50cf8d5d31d.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Badmotorfinger SOMMS EP",
					"playcount": 38680,
					"url": "https://www.last.fm/music/Soundgarden/Badmotorfinger+SOMMS+EP",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/7d553c23f770449391f6b35e4ca4be6e.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/7d553c23f770449391f6b35e4ca4be6e.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/7d553c23f770449391f6b35e4ca4be6e.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/7d553c23f770449391f6b35e4ca4be6e.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Superunknown (Commentary)",
					"playcount": 31506,
					"url": "https://www.last.fm/music/Soundgarden/Superunknown+(Commentary)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/0c2b4c70ef75672cc276aea42db0ae1f.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/0c2b4c70ef75672cc276aea42db0ae1f.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/0c2b4c70ef75672cc276aea42db0ae1f.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/0c2b4c70ef75672cc276aea42db0ae1f.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Live to Rise - Single",
					"playcount": 37660,
					"url": "https://www.last.fm/music/Soundgarden/Live+to+Rise+-+Single",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/1b031a3c269c49809adea17eb65bc020.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/1b031a3c269c49809adea17eb65bc020.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/1b031a3c269c49809adea17eb65bc020.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/1b031a3c269c49809adea17eb65bc020.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Telephantasm (Explicit)",
					"playcount": 32736,
					"url": "https://www.last.fm/music/Soundgarden/Telephantasm+(Explicit)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/e2157ff9eae54f9a941183dc97595edc.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/e2157ff9eae54f9a941183dc97595edc.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/e2157ff9eae54f9a941183dc97595edc.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/e2157ff9eae54f9a941183dc97595edc.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Black Hole Sun/New Damage/Blind Dogs",
					"playcount": 7410,
					"url": "https://www.last.fm/music/Soundgarden/Black+Hole+Sun%2FNew+Damage%2FBlind+Dogs",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/720268fdee2bc1a442c2722c7fdd7f4a.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/720268fdee2bc1a442c2722c7fdd7f4a.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/720268fdee2bc1a442c2722c7fdd7f4a.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/720268fdee2bc1a442c2722c7fdd7f4a.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Superunknown (20th Anniversary Super Deluxe)",
					"playcount": 49699,
					"url": "https://www.last.fm/music/Soundgarden/Superunknown+(20th+Anniversary+Super+Deluxe)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/dfd311d3e5e318c283a27ee459306a4f.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/dfd311d3e5e318c283a27ee459306a4f.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/dfd311d3e5e318c283a27ee459306a4f.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/dfd311d3e5e318c283a27ee459306a4f.png",
							"size": "extralarge"
						}
					]
				},
				{
					"name": "Suffocate (Live 1991)",
					"playcount": 14478,
					"url": "https://www.last.fm/music/Soundgarden/Suffocate+(Live+1991)",
					"artist": {
						"name": "Soundgarden",
						"mbid": "153c9281-268f-4cf3-8938-f5a4593e5df4",
						"url": "https://www.last.fm/music/Soundgarden"
					},
					"image": [
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/34s/61b1f5d31137c4eb2fc3dcf74b133846.png",
							"size": "small"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/64s/61b1f5d31137c4eb2fc3dcf74b133846.png",
							"size": "medium"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/174s/61b1f5d31137c4eb2fc3dcf74b133846.png",
							"size": "large"
						},
						{
							"#text": "https://lastfm.freetls.fastly.net/i/u/300x300/61b1f5d31137c4eb2fc3dcf74b133846.png",
							"size": "extralarge"
						}
					]
				}
			],
			"@attr": {
				"artist": "Soundgarden",
				"page": "1",
				"perPage": "50",
				"totalPages": "549",
				"total": "27408"
			}
		}
	}
	```

??? warning "Example response of an artist/track that doesnt exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=artist.getTopAlbums&artist=artistthatdoesntexist&track=i%20wish&api_key=YOUR_API_KEY&format=json
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

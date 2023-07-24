Returns the top tags chart.

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

??? note "Example response"

	| Parameter | Value         |
	| --------- | ------------- |
	| limit     | 10            |
	| api_key   | YOUR_API_KEY  |
	| format    | json          |

	HTTP status: `200 OK`

	```
	https://ws.audioscrobbler.com/2.0/?method=chart.getTopTags&limit=10&api_key=YOUR_API_KEY&format=json
	```
	```json
	{
		"tags": {
			"tag": [
				{
					"name": "rock",
					"url": "https://www.last.fm/tag/rock",
					"reach": "399561",
					"taggings": "4026340",
					"streamable": "1",
					"wiki": {}
				},
				{
					"name": "electronic",
					"url": "https://www.last.fm/tag/electronic",
					"reach": "258618",
					"taggings": "2443112",
					"streamable": "1",
					"wiki": {}
				},
				{
					"name": "seen live",
					"url": "https://www.last.fm/tag/seen+live",
					"reach": "82188",
					"taggings": "2160996",
					"streamable": "1",
					"wiki": {}
				},
				{
					"name": "alternative",
					"url": "https://www.last.fm/tag/alternative",
					"reach": "264913",
					"taggings": "2114188",
					"streamable": "1",
					"wiki": {}
				},
				{
					"name": "indie",
					"url": "https://www.last.fm/tag/indie",
					"reach": "257507",
					"taggings": "2044341",
					"streamable": "1",
					"wiki": {}
				},
				{
					"name": "pop",
					"url": "https://www.last.fm/tag/pop",
					"reach": "230530",
					"taggings": "2031581",
					"streamable": "1",
					"wiki": {}
				},
				{
					"name": "female vocalists",
					"url": "https://www.last.fm/tag/female+vocalists",
					"reach": "168721",
					"taggings": "1621018",
					"streamable": "1",
					"wiki": {}
				},
				{
					"name": "metal",
					"url": "https://www.last.fm/tag/metal",
					"reach": "157331",
					"taggings": "1280182",
					"streamable": "1",
					"wiki": {}
				},
				{
					"name": "alternative rock",
					"url": "https://www.last.fm/tag/alternative+rock",
					"reach": "168563",
					"taggings": "1202962",
					"streamable": "1",
					"wiki": {}
				},
				{
					"name": "jazz",
					"url": "https://www.last.fm/tag/jazz",
					"reach": "148570",
					"taggings": "1173582",
					"streamable": "1",
					"wiki": {}
				}
			],
			"@attr": {
				"page": "1",
				"perPage": "10",
				"totalPages": "280685",
				"total": "2806844"
			}
		}
	}
	```

[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create

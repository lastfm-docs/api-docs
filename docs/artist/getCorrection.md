Get the metadata and tracklist for an album on Last.fm using the album name or a musicbrainz id.

No authentication required.

## Parameters

| Method        | Type                                                                                              | Default | Required                      | Description                                                                                                           |
| ------------- | ------------------------------------------------------------------------------------------------- | ------- | ----------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `artist`      | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none`  | :white_check_mark:          | The artist which's album should be fetched.                                                                           |
| `track`       | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none`  | :white_check_mark:        | The track that should be fetched.                                                                                     |
| `api_key`     | [token](https://www.last.fm/api/account/create)                                                   | `none`  | :white_check_mark:            | A Last.fm API key.                                                                                                    |

## Responses

Errors:

- 6 : Invalid parameters - Your request is missing a required parameter
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
	| artist    | Skee-Lo       |
	| track     | I wish        |
	| api_key   | YOUR_API_KEY  |

	HTTP status: `200 OK`

	```
	http://ws.audioscrobbler.com/2.0/?method=track.getcorrection&artist=skee-lo&track=i%20wish&api_key=YOUR_API_KEY&format=json
	```

	```json
	{
		"corrections": {
			"correction": {
				"track": {
					"name": "I Wish",
					"mbid": "ccb9326a-6f9f-48b1-a097-1210dd14e119",
					"url": "https://www.last.fm/music/Skee-Lo/_/I+Wish",
					"artist": {
						"name": "Skee-Lo",
						"mbid": "9341a67c-4f0c-43c2-9ec4-c222d2cb97f3",
						"url": "https://www.last.fm/music/Skee-Lo"
					}
				},
				"@attr": {
					"index": "0",
					"artistcorrected": "0",
					"trackcorrected": "0"
				}
			}
		}
	}

	```

??? warning "Example response of an artist/track that doesnt exist"
    HTTP status: `200 OK`

    ```
    http://ws.audioscrobbler.com/2.0/?method=track.getcorrection&artist=artistthatdoesntexist&track=i%20wish&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
			"corrections": {
				"correction": {
					"track": {
						"url": "",
						"artist": {
							"url": ""
						}
					},
					"@attr": {
						"index": "0",
						"artistcorrected": "0",
						"trackcorrected": "0"
					}
				}
			}
    }   
    ```

Returns metadata information for a tag.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `tag` | [string][string] | `none` | :white_check_mark: | The tag name to search information for.
| `lang` | [string][string] | `en` | :negative_squared_cross_mark: | The language which will be used in the response for the tag. Requires an ISO 639 alpha-1 code.
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

    | Parameter | Value        |
    | --------- | ------------ |
    | tag       | metal        |
    | api_key   | YOUR_API_KEY |
    | format    | json         |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=tag.getInfo&tag=metal&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
      "tag": {
        "name": "metal",
        "total": 1279720,
        "reach": 157277,
        "wiki": {
          "summary": "Metal is a subgenre of rock music that developed in the late 1960s and early 1970s. With roots in blues-rock and psychedelic rock, the bands that created heavy metal developed a thick, massive sound characterized by highly amplified distortion and extended guitar solos. Allmusic states that, “of all rock & roll’s myriad forms, heavy metal is the most extreme in terms of volume, machismo and theatricality.”\n\nHeavy metal has long had a worldwide following of fans known as metalheads or headbangers.",
          "content": "Metal is a subgenre of rock music that developed in the late 1960s and early 1970s. With roots in blues-rock and psychedelic rock, the bands that created heavy metal developed a thick, massive sound characterized by highly amplified distortion and extended guitar solos. Allmusic states that, “of all rock & roll’s myriad forms, heavy metal is the most extreme in terms of volume, machismo and theatricality.”\n\nHeavy metal has long had a worldwide following of fans known as metalheads or headbangers. Although early heavy metal bands such as Black Sabbath, Led Zeppelin and Deep Purple attracted large audiences, they were often critically reviled at the time. A status common throughout the history of the genre. In the mid-1970s, Judas Priest helped spur the genre’s evolution by discarding much of its blues influence. Bands in the New Wave of British Heavy Metal such as Iron Maiden and Motörhead followed in a similar vein, introducing a punk rock sensibility and an increasing emphasis on speed. ..."
        }
      }
    }
    ```

??? warning "Example response of a tag that doesn't exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=tag.getInfo&tag=thistagdoesntexist&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "tag": {
        "name": "thistagdoesntexist",
        "total": 0,
        "reach": 0,
        "wiki": {
          "summary": " <a href=\"https://www.last.fm/tag/thistagdoesntexist\">Read more on Last.fm</a>.",
          "content": ""
        }
      }
    }
    ```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[key]: https://www.last.fm/api/account/create
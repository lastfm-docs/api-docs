Get a list of available charts for this tag, expressed as date ranges which can be sent to the chart services.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `tag` | [string][string] | `none` | :white_check_mark: | The tag name to search information for.
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

## Examples
??? note "Example response"

    | Parameter | Value        |
    | --------- | ------------ |
    | tag       | metal        |
    | api_key   | YOUR_API_KEY |
    | format    | json         |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=tag.getWeeklyChartList&tag=metal&api_key=YOUR_API_KEY&format=json
    ```


    ```json
    {
      "weeklychartlist": {
        "chart": [
          {
            "#text": "",
            "from": "1108296000",
            "to": "1108900800"
          },
          {
            "#text": "",
            "from": "1108900800",
            "to": "1109505600"
          },
          {
            "#text": "",
            "from": "1109505600",
            "to": "1110110400"
          },
          ... and 952 more
        ],
        "@attr": {
          "tag": "metal"
        }
      }
    }
    ```

??? warning "Example response of a tag that doesn't exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=tag.getWeeklyChartList&tag=thistagdoesntexist&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "weeklychartlist": {
        "chart": [
          {
            "#text": "",
            "from": "1108296000",
            "to": "1108900800"
          },
          {
            "#text": "",
            "from": "1108900800",
            "to": "1109505600"
          },
          {
            "#text": "",
            "from": "1109505600",
            "to": "1110110400"
          },
          ... and 958 more
        ],
        "@attr": {
          "tag": "thistagdoesntexist"
        }
      }
    }
    ```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[key]: https://www.last.fm/api/account/create
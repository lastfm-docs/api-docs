# Bugs
The last.fm API is by no means updated or maintained regularly, due to this, responses are often riddled with inconsistency and is not up to standards. This page aims to document these bugs, and similar instances of malformed responses and be a reference for developers trying to make last.fm apps and tools.

Every part of this page documents a different case and can be linked to individually to help make helping newcomers feasible.

## Status Codes
Last.fm has a few bugs to iron out with its return headers, one of these causes the API to return inaccurate HTTP response codes in the return header. Some requests do not return the requested resource but still emit a HTTP 200 OK code.
The `getTopTags` method for example, returns an empty array as a response if the resource has no tags, but still emits an OK in the response header. 
To prevent your apps breaking, all responses must be checked as just relying on return headers is not enough to validate your response.

Methods that currently exhibit this behaviour
- track.getTopTags
- album.getTopTags
- artist.getTopTags

## Attribute Fields
As per [this page](https://www.last.fm/api/rest) in the official documentation, last.fm serves its JSON responses as converted XML responses, this is done automatically and leads to mistructed JSON, the most common occurrence with this is the presence of fields in the form of attributes to JSON objects, these are attached to JSON objects and can be accessed by looking through the JSON using the title as the property name.

For example the [user.getInfo](https://lastfm-docs.github.io/api-docs/user/getInfo/) method has a nested JSON objected (`registered`) that includes information about when a user account was created. This includes a text
 field named "#text", this property can be accessed by using the title of the value (`#text`) as a key.
```
+ registered["#text"]
- registered.text
```

Similarly @attr fields can be accessed by using `"@attr"` as a key.

## Mistitled Fields
The official documentation has schemas that reflect some fields to have data they do not. For example, the `getTopArtists` methods when called upon the `geo` endpoint should return a field for the number of listeners that the artist has in the requested country. This field is missing in the response and is replaced by a `listeners` field that reflects an artist's global listener count, not his listeners in that country as it should.

Similarly certain fields containing time information are often titled differently in the documented schemas, in actuality, they are placed in a "uts" field. UTS is an abbrevation for UNIX Timestamp, this is not a common title for it.

# Bugs
The last.fm API is by no means updated or maintained regularly, due to this, responses are often riddled with inconsistency and is not up to standards. This page aims to document these bugs, and similar instances of malformed responses and be a reference for developers trying to make last.fm apps and tools.

Every part of this page documents a different case and can be linked to individually to help make helping newcomers feasible.

## Attribute fields
As per [this page](https://www.last.fm/api/rest) in the official documentation, last.fm serves its JSON responses as converted XML responses, this is done automatically and leads to mistructed JSON, the most common occurrence with this is the presence of fields in the form of attributes to JSON objects, these are attached to JSON objects and can be accessed by looking through the JSON using the title as the property name.

For example the [user.getInfo](https://lastfm-docs.github.io/api-docs/user/getInfo/) method has a nested JSON objected (`registered`) that includes information about when a user account was created. This includes a text
 field named "#text", this property can be accessed by using the title of the value (`#text`) as a key.
```
+ registered["#text"]
- registered.text
```

Similarly @attr fields can be accessed by using `"@attr"` as a key.

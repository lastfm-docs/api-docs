Signatures are an extra parameter you have to add to any API calls that use authentication.

They consist of almost all of your parameters together, in an alphabetical order and hashed as an MD5. They can be very difficult to get right the first time.

## Step by step: How to create a signature when getting a sessionkey

Here are the parameters we will be using for this example:

| Parameter | Value                |
|-----------|--------------------- |
| method    | auth.getSession      |
| api_key   | YOUR_API_KEY         |
| token     | YOUR_REQUESTED_TOKEN |
| format    | json                 |

---

Gather all the parameters that you want to use in your API call.

Now order them alphabetically and make sure to exclude the `format` parameter.

| Parameter | Value                |
|-----------|--------------------- |
| api_key   | YOUR_API_KEY         |
| method    | auth.getSession      |
| token     | YOUR_REQUESTED_TOKEN |

---

Now that you have this you need to make one long string of all the keys and values.

```
api_keyYOUR_API_KEYmethodauth.getSessiontokenYOUR_REQUESTED_TOKEN
```

---

When you have this string, all you need to do is add the secret you got when creating your last.fm application. 

Make sure to add this secret without a key, just the value is enough. In this case our secret is `YOUR_SECRET`.

```
api_keyYOUR_API_KEYmethodauth.getSessiontokenYOUR_REQUESTED_TOKENYOUR_SECRET
```

---

Now, you need to convert has this to md5. Make sure you use UTF-8 encoding.

If you would encode the string above you should get the following value:

```
94539006DE89B3C6B3C030BB1E52B9C4
```

---

Add this signature to your parameters, with the `api_sig` key. Your final parameters should now look like this:

| Parameter | Value                            |
|-----------|----------------------------------|
| method    | auth.getSession                  |
| api_key   | YOUR_API_KEY                     |
| token     | YOUR_REQUESTED_TOKEN             |
| format    | json                             |
| api_sig   | 94539006DE89B3C6B3C030BB1E52B9C4 |


## Code example: C\#

It might be helpful an actual implementation, so here is an example that is used in [.fmbot](https://github.com/fmbot-discord/fmbot) for calls that need a signature.

```csharp

if (generateSignature)
{
    var signature = new StringBuilder();

    foreach (var (key, value) in parameters
                                    .OrderBy(o => o.Key)
                                    .Where(w => !w.Key.Contains("format")))
    {
        signature.Append(key);
        signature.Append(value);
    }

    signature.Append(this._secret);

    parameters.Add("api_sig", CreateMd5(signature.ToString()));
}
```

Function that creates MD5 hash:

```csharp
private static string CreateMd5(string input)
{
    using var md5 = System.Security.Cryptography.MD5.Create();
    var inputBytes = Encoding.UTF8.GetBytes(input);
    var hashBytes = md5.ComputeHash(inputBytes);

    var sb = new StringBuilder();
    foreach (var t in hashBytes)
    {
        sb.Append(t.ToString("X2"));
    }
    return sb.ToString();
}
```
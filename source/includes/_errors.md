# Errors

When an error occurs during an API request, you will receive:

- An HTTP error status (in the 400-500 range)
- A JSON response containing more information about the error

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- The resource requested is hidden for administrators only.
404 | Not Found -- The specified resource could not be found.
405 | Method Not Allowed -- You tried to access a resources with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
429 | Too Many Requests -- You're requesting too many Events! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.

### Error Messages
A typical error response is a JSON with many fields.

```shell
curl "https://api.talentgarden.com/v1/users?page=asdf&per_page=poasdf
```
> The above command returns JSON structured like this:

```json
{
    "message": "Invalid parameters",
    "details": [
        {
            "value": "poasdf",
            "msg": "Must Be An Integer",
            "param": "per_page",
            "location": "query"
        },
        {
            "value": "asdf",
            "msg": "Must Be An Integer",
            "param": "page",
            "location": "query"
        }
    ]
}
```
Errors fields | Meaning
---------- | ---------
message | Error description.
details | Object with more information
code | Id to identified a spacial error, could not be present

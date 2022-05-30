# Authentication


<!-- ## API Key
> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "x-api-key: YOUR_API_KEY"
```

> Make sure to replace `YOUR_API_KEY` with your API key.

API key allows to access to some of our API services.
This kind of authentication is often used for server to server comminication because API Key does not expire. For this way we highly reccomend to not expose the API Key client-side.

You can request an API key <a href='mailto:digital@talentgarden.org?subject=API key request'>getting in touch with us</a>.

Talent Garden expects the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: YOUR_API_KEY`

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your personal API key.
</aside>

Your API keys carry many privileges, so be sure to keep them secure! 
Do not share your secret API keys in publicly accessible areas such as GitHub, client-side code, and so forth. -->

### JSON Web Token
> To authorize, use this code:

```js
// Make the api call with this config 
const config = {
  headers: {
    accept: 'application/json',
    Authorization: 'Bearer YOUR_JWT'
  },
};
```

> Make sure to replace `YOUR_JWT` with your JWT.

JSON Web Token (JWT) authentication is used to call API Services personifying a specific logged user.
The JWT must be issued from one of our applications registered in our Auth0 tenants.

To make calls to the API, send the JWT in the Authorization HTTP header using the Bearer authentication scheme.
Talent Garden expects the JWT to be included in all API requests from the client in a header that looks like the following:

`Authorization: Bearer YOUR_JWT`

<aside class="notice">
You must replace <code>YOUR_JWT</code> a valid Auth0 issued token.
</aside>

You can request an Auth0 OAuth2 client <a href='mailto:digital@talentgarden.org?subject=Auth0 OAuth2 client request'>getting in touch with us</a>.
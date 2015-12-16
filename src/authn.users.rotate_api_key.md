## Rotate API Key [/api/authn/users/api_key{?id}]

### Rotate the API key [PUT]

This method replaces the API key of an authn user with a new, securely random 
API key. The new API key is returned as the response body.

This request must be authenticated by Basic authentication using the existing 
API key or password of the user. A Conjur access token cannot be used to rotate
the API key.

**Permissions required**:

Any authenticated identity can rotate its own API key, providing it's coming from a valid IP address.
Basic authorization (username plus password or API key) must be provided.

An authenticated identity can rotate the API key of a different user if it has `update` privilege on the
other user's resource. In this case, access token is accepted as authentication.

### Supported version

Conjur 4.6 or higher.

---

**Headers**

|Field|Description|Example|
|----|------------|-------|
|Authorization|HTTP Basic Auth|Basic YWRtaW46cGFzc3dvcmQ=|

**Response**

|Code|Description|
|----|-----------|
|200|The response body is the API key|
|401|The Basic auth credentials were not accepted|

+ Parameters
    + id: alice (string, optional) - Id of the user to rotate. If not provided, the current authenticated user's API
    key is rotated.

+ Request
    + Headers
    
        ```
        Authorization: Basic YWRtaW46cGFzc3dvcmQ=
        ```
        
+ Response 200 (text/html; charset=utf-8)

    ```
    14m9cf91wfsesv1kkhevg12cdywm2wvqy6s8sk53z1ngtazp1t9tykc
    ```
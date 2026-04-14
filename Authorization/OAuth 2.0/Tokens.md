
**Tokens** are credentials that represent authorization 

* Used by a client to access protected resources on behalf of a user instead of using a username and password
* Can be expired or revoked if compromised
* Can be restricted using scopes

## Access Tokens

Access tokens are short-lived credentials that are used to access protected resources

* Expire quickly (Minutes to hours)
* Can be either opaque or structured
* Sent in HTTP requests within the Authorization header (`Authorization: Bearer ACCESS_TOKEN`)

## Refresh Tokens

Refresh tokens are long-lived tokens used to obtain new access tokens

* Allows re-authentication without user interaction
* Stored securely by the client

Flow:
1. Access token expires
2. Client sends refresh token to authorization server
3. Server returns a new access token
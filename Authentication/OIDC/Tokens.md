
## ID Token

**ID tokens** are security tokens that are used to represent the identity of an authenticated user in OIDC rather than access APIs

* Issued by the IdP after a successful login
* Consumed by the client application to verify who the user is (Answers the *Who is the user that just authenticated* question)
* Always in a [[JSON Web Token|JWT Token]] format (`header.payload.signature`)
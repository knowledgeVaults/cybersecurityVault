
**JWT** is a compact and self-contained token format that's used to securely transmit information between parties

* Stateless (All required info is stored inside the token so no need to store sessions on the server)
* Portable (Can be used across multiple services)
* Verifiable (The integrity is maintained via signatures)
* Not encrypted by default

JWT flow:
1. The user logs in
2. The server generates a JWT
3. The client stores the token
4. The client sends it in their HTTP request's header (`Authorization: Bearer TOKEN`)
5. The server verifies the signature and claims (If valid, then the request is accepted)

## Token Structure

* Each part of the token is base64-encoded

JWT structure:
```Text
HEADER
.
PAYLOAD
.
SIGNATURE
```

JWT example:
```Text
eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9
.
eyJzdWIiOiIxMjM0NTY3ODkwIiwiZW1haWwiOiJqb2huQGV4YW1wbGUuY29tIiwiaXNzIjoiaHR0cHM6Ly9hdXRoLmV4YW1wbGUuY29tIiwiYXVkIjoiY2xpZW50X2lkIiwiZXhwIjoxNzEwMDAwMDAwLCJpYXQiOjE3MDk5OTAwMDB9
.
QmFzZTY0VVJMLVNJR05BVFVSRS1FWEFNUExF
```

### Header

Contains metadata about the token

### Payload (Claims)

Contains the actual data (claims)

### Signature

Used to verify that the token was issued by a trusted source and has not been modified

* Created using both the header and payload: `sign(base64(header) + "." + base64(payload), private_key_or_secret)`
* Acts as a secret or private key
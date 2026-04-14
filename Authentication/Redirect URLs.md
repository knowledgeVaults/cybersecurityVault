
**Redirect**/**Callback URLs** is the address an authorization server sends the user back to after they've successfully authenticated

```
App sends user to the auth provider → User logs in → Auth provider redirects them back to the app via the redirect URL along with an authorization code or token attached in the URL
```

* The URL must be pre-registered with the auth provider otherwise attackers can tamper with the redirect parameter and send the auth code to a server under their control (**Open redirect attack**)
# /api/auth/
# https://cvrapi.loca.lt/api/auth/

Auth handles the authorization of users, whether on the web, while using the API, or while playing CVR.

# /auth/create
## Type: POST
## Authorization: None

Pass a JSON file along with this request containing the following data:

{
     "username": "[Your username here]",
     "nickname": "[Your nickname here (Optional, will default to username.)]",
     "password": "[Your password here",
}

If the server responds with 200 OK, your account has been successfully created.

# /auth/login
## Type: POST
## Authorization: None

Pass a JSON file along with this request containing the following data:

{
     "username": "[Your username here (Not case sensitive)]",
     "password": "[Your password here (CASE SENSITIVE)]"
}

The server will respond with 200 OK and the returned JSON data will contain an access token, which can be used with BEARER authorization.

The server will respond with 403 Not Authorized and no token under the following conditions:

-The account you inputted has an active ban.
-Your password was incorrect.

The server will respond with 404 Not Found and no token if the username you inputted does not match an account in the database.

# /auth/check
## Type: POST
## Authorization: Bearer + Access Token

No JSON data is necessary to call this request.

Server will respond with 403 Forbidden if the provided token is not valid.
Server will respond with 200 OK if the provided token is valid.
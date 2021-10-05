# /api/accounts/
## https://cvrapi.loca.lt/api/accounts

The Accounts endpoints handles utility functions for getting and setting information about users.

# /accounts/:username/id
## Type: GET
## Authorization: None

No JSON data is necessary to send along with this request.

If an account with the :username property as its username exists, the server will respond with 200 OK with its account ID.

If an account does not exist that has that username, the server will respond with 404 Not Found and no extra data.

# /accounts/:id/public
## Type: GET
## Authorization: None

Gets the public user data of the user specified.

If an account does not exist with that ID, the server will respond with 404 Not Found

Otherwise, the server will respond with 200 OK and the contents of the "public" section of the player's user data file.
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

Otherwise, the server will respond with 200 OK and the ID of the player in "id" of the returned json data.

# /accounts/bio
## Type: POST
## Authorization: Bearer <InGameToken>

## Content-Type: application/json

## Content Example:
{
     "bio": "<DesiredBio>"
}

Sets the bio of the authorized account.
Bios cannot contain profanity / slurs or be over 2000 characters.

Responds with 200 OK if the operation suceeds, and 403 Forbidden if the bio contains profanity or other disallowed phrases.

# /accounts/pronouns
## Type: POST
## Authorization: Bearer <InGameToken>

## Content-Type: application/json

## Content Example:
{
     "pronouns": "<DesiredPronouns>"
}

Sets the pronouns of the authorized account.
Pronouns are an integer that selects an item from the following list of pronouns:

"He/Him", 
"She/Her", 
"They/Them", 
"He/they", 
"She/they", 
"He/she", 
"He/she/they", 
"Ask me"

If an invalid index is selected, the server responds with HTTP 400.

If the operation suceeds, the server responds with HTTP 200 OK.

# /accounts/:id/private
## Type: GET
## Authorization: Bearer <InGameToken>

Returns the associated private data of the account id specifed.

If the id sent does not match the authorized token, the server will respond with HTTP 403 Forbidden.

If the id sent does not exist in the database, the server will respond with HTTP 404 Not Found.

If the operation suceeds, the server will respond with HTTP 200 OK and the JSON data of the "private" section of the account data specified.

# /accounts/nickname
## Type: POST
## Authorization: Bearer <InGameToken>

## Content-Type: application/json
## Content Example:
{
     "nickname": "<DesiredNickname>"
}

Sets the nickname of the authorized token to the specified nickname.

If the nickname is null or empty, the server will respond with HTTP 400.
If the nickname fails the profanity filter, the server will respond with HTTP 403 Forbidden.
If the operation suceeds, the server will respond with HTTP 200 OK.

# /accounts/tag
## Type: POST
## Authorization: Bearer <InGameToken>

## Content-Type: application/json
## Content Example:
{
     "tag": "<DesiredTag>"
}

Sets the tag of the authorized token to the specifed tag.

If the tag is null or empty, or the authorized token's user does not possess that tag, the server will respond with HTTP 400.
If the operation suceeds, the server will respond wtih HTTP 200 OK.

# /accounts/outfit
## Type: POST
## Authorization: Bearer <InGameToken>

## Content-Type: application/json
## Content Example:
{
     "type": "<DesiredType>,
     "id": "<DesiredID>"
}

Used to set a single item of clothing on the authorized player.

Returns HTTP 400 if the player does not own the item, or if the item type does not exist.

Returns HTTP 200 OK if the operation suceeds.
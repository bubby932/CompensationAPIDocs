# /api/notifications
## https://cvrapi.loca.lt/api/notifications
The /notifications endpoint is used to get and send notifications in-game and on the CVR website to users.

# /notifications/get
## Type: GET
## Authorization: Bearer <InGameToken>

Returns the JSON Array of the token user's pending notifications.

Returns 200 OK with the data formatted as follows:
[
     {
          <NOTIFICATION DATA HERE>
     },
     {
          <NOTIFICATION DATA HERE>
     }
]
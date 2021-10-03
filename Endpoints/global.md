# /api/global
# https://cvrapi.loca.lt/api/global

The Global endpoint is used to get global data, accessable by anyone. This information is synced between all users, and can be accessed without authorization necessary.

# /global/:key
## Type: GET
## Authorization: None

If the server has global data corresponding to the :key property, the server will respond with 200 OK and the data associated with the :key property.

If the server does not have any data associated with they :key property, it will respond with 404 Not Found and no data.
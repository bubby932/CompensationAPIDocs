# /api/social/
## http://api.compensationvr.tk/api/social

# /api/social/imgfeed
## Type: GET
## Authorization: None

## Content-Type: application/json
## Content Example:

{
     "count": 50,
     "offset": 0,
     "order": 0
}

If the 'order' parameter is equal to 0, the images sort from newest to oldest.
If the 'order parameter is not equal to 0, the images sort from oldest to newest.

The 'count' parameter specifies the number of posts to get.
The 'offset' parameter offsets the selection from the most or least recent posts by it's value.

If any of the above parameters are missing, the API will respond with HTTP 400.
If no images are present on the API, the API will respond with HTTP 500 Internal Server Error.
If you specify too high of an offset or count it will be adjusted to fit the number of available images.

If the operation is successful, the API will respond with JSON data of all the requested photos.
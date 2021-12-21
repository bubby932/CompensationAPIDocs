# /img/
## http://api.compensationvr.tk/api/

The img endpoint is used to upload and retrieve images from the CVRAPI.

# /img/upload/:others/:roomId/:roomName
## Type: POST
## Authorization: Bearer <Token>

## Content-Type: multipart/form-data
## Content Example:

"img": file.png

Returns HTTP 200 OK if the image upload is successful.
Returns HTTP 500 Internal Server Error if the server has an issue.
Returns HTTP 400 if you miss a parameter.

Only one file upload per request is permitted.
File must have a MIME type of image/png.

# /img/:id
## Type: GET
## Authorization: None

Returns HTTP 200 OK and the image specified if the image exists.
Returns HTTP 404 Not Found if the image does not exist.
Returns HTTP 500 on any other error.

# /img/:id/info
## Type: GET
## Authorization: None

Returns HTTP 200 OK and the information about the image specified if it exists.
Returns HTTP 404 Not Found if the image does not exist.
Returns HTTP 500 on any other error.
## Publish Profiles

_All messages SHOULD rely only on standardized names (data/action) based on shared vocabularies._

NOTE: This example relies on the `link' header from https://tools.ietf.org/html/rfc8288

### HTTP Interaction

```
#### Sucessful Profile Negotiation
*** REQUEST
GET /accounts HTTP/1.1
  Host: example.org
  Accept: application/vnd.uber+xml
  Link: <http://alps.io/banking/v3>;rel="profile">
  
***RESPONSE
HTTP/1.1 200 OK
  Content-Type: application/vnd.uber+xml
  Link: <http://alps.io/banking/v3>;rel="profile">
  
  <uber version="1.0">
    ...
  </uber>

#### Failed Profile Negotitation
*** REQUEST
GET /accounts HTTP/1.1
  Host: example.org
  Accept: application/vnd.uber+xml
  Link: <http://alps.io/banking/v4>;rel="profile">
  
***RESPONSE
HTTP/1.1 400 Bad Request
  Content-Type: application/vnd.uber+xml
  Link: <http://alps.io/banking/v2>;rel="profile">
  
  <uber version="1.0">
   <data id="error" text="Requested Profile Unsupported" />
  </uber>

  
```

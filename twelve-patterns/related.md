## Related Link

_Services SHOULD return a `related` LINK that responds with ALL the possible actions for this context._

NOTE: This example uses the `related` link relation defined in https://tools.ietf.org/html/rfc4287

### HTTP Interaction

```
*** REQUEST
GET /orders/123 HTTP/1.1
  Host: example.org
  Accept: application/vnd.hal+json
  
*** RESPONSE
HTTP/1.1 200 OK
  Content-Type: application/vnd.hal+json
  Content-Length: XXXX
  
{
  "_links": {
    "self": {"href" : "..."},
    "approve": {"href" : "..."},
    "related": {"href" : "/orders/123?related"}
    ...
}  

*** REQUEST
GET /orders/123?related HTTP/1.1
  Host: example.org
  Accept: application/vnd.hal+json
  
*** RESPONSE
HTTP/1.1 200 OK
  Content-Type: application/vnd.hal+json
  Content-Length: XXXX
  
{
  "_links": {
    "self": {"href" : "..."},
    "approve": {"href" : "..."},
    "cancel": {"href" : "..."},
    "modify": {"href" : "..."},
    "transfer": {"href" : "..."},
    "review": {"href" : "..."},
    "rush": {"href" : "..."},
    "related": {"href" : "/orders/123?related"}
    ...
}  

```

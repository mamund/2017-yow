## Provide MRU

_Services SHOULD return the most recently-used (MRU) LINKS and FORMS in all responses._

### HTTP Interactions

```
#### execute a SEARCH
*** REQUEST
GET /orders/search HTTP/1.1
  Host: example.org
  Accept: application/vnd.hal+json
  
*** RESPONSE
HTTP/1.1 200 OK
  Content-Type: application/vnd.hal+json
  Content-Length: XXXX
  
{
  "_links": {
    "self": {"href" : "..."},
    "search": {"href" : "/orders/search"}
    ...
}  

#### execute an ADD
*** REQUEST
POST /orders/ HTTP/1.1
  Host: example.org
  Accept: application/vnd.hal+json
  
*** RESPONSE
HTTP/1.1 200 OK
  Content-Type: application/vnd.hal+json
  Content-Length: XXXX
  
{
  "_links": {
    "self": {"href" : "..."},
    "search": {"href" : "..."},
    "add": {"href" : "..."}
    ...
}  

```

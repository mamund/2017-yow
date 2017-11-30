## State Watch

_Services SHOULD allow clients to subscribe to WATCH VALUES so that clients can determine "done."_

NOTE: This implementation uses the HTTP *Prefer* Header defined in https://tools.ietf.org/html/rfc7240

### HTTP Interaction
```
*** REQUEST
POST /heat-mgmt HTTP/1.1
     Host: example.org
     Content-Type: application/x-www-form-urlencoded
     Accept: application/vnd.collection+json
     Prefer: state-watch="sensor5,temp13"

     sensor5=increase by .5c;
     
*** RESPONSE
HTTP/1.1 200 OK
     Content-Type: application/collection+json
     Preference-Applied: state-watch="sensor5,sensor13"
     Content-Location: /heat-mgmt
     
     {"collection" : 
       {
         "items" : [
           ...
           {
             "href" : "/heat-mgmt/sensor5",
             data: [
               {"name" : "device", "value" : "sensor5"},
               {"name" : "reading", "value" : "14.5c"}
             ]
           }
           ...
         ]
       }
     }

```

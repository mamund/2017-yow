## Use Navigation

_Services SHOULD provide `next` and `previous` LINK elements to handle multi-step workflow along with `cancel`, `restart`, & `done`._

### Client-side Code Example

```javascript
// evaulate options
var localState = "";
var msg = getCurrentResponseBody();
var state = "next";
switch (msg) {
  case msg.findNavigation("done"):
    localState = "done";
    break;
  case msg.findNavigation("cancel"):
    if(localState==="cancel" {
      break;
    ]
  case "msg.findNavigation("retart"):
    if(localState==="restart") {
      break;
    }
}
```

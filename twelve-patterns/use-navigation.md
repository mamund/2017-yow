## Use Navigation

_Services SHOULD provide `next` and `previous` LINK elements to handle multi-step workflow along with `cancel`, `restart`, & `done`._

### Client-side Code Example

```javascript
// evaulate options
var lookingFor = "next";
var msg = getCurrentResponseBody();
switch (msg) {
  case msg.findNavigation("done"):
    if(lookingFor==="done") {
      processDone(msg);
      break;
    }
  case msg.findNavigation("cancel"):
    if(lookingFor==="cancel" {
      processCancel(msg);
      break;
    }
  case msg.findNavigation("restart"):
    if(lookingFor==="restart") {
      processRestart(msg);
      break;
    }
  case msg.findNavigation("previous"):
    if(lookingFor==="previous") {
      processPrevious(msg);
      break;
    }
  case msg.findNavigation("next"):
    if(lookingFor==="next") {
      processNext(msg);
      break;
    }
}
```

## Use Navigation

_Services SHOULD provide `next` and `previous` LINK elements to handle multi-step workflow along with `cancel`, `restart`, & `done`._

### Client-side Code Example

```javascript
// evaulate options
var lookingFor = "next";
var msg = getCurrentResponseBody();
switch (lookingFor) {
  case "done":
    if(msg.findNavigation(lookingFor)) {
      processDone(msg);
    }
    break;
  case "cancel":
    if(msg.findNavigation(lookingFor)) {
      processCancel(msg);
    }
    break;
  case "restart":
    if(msg.findNavigation("restart")) {
      processRestart(msg);
    }
    break;
  case "previous":
    if(msg.findNavigation("previous")) {
      processPrevious(msg);
    }
    break;
  case "next":
    if(msg.findNavigation("next")) {
      processNext(msg);
    }
    break;
  default: // give up
    lookingFor = "cancel";
    break;
}
```

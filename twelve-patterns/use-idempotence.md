## Use Idempotence

_All network requests SHOULD be idempotent in order to allow clients to safely repeat them when response is unclear._

### Client-Side Example

```javascript
var maxRequests = 5;
var options = {
  url: 'http://www.exmple.org/users/123',
  method: "put",
  body = user.formFields();
  timeout: 5000
}

function idempotentRequest(attempt){
  request(options, function(error,response,body){
    if(error){
      console.log(error);
      if(attempt==maxRequests)
        return;
      else
        idempotentRequest(attempt+1);
    }
    else {
      //do something with result
    }
  });
}

idempotentRequest(1);

```

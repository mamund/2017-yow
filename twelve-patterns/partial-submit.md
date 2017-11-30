## Partial Submit

_Services SHOULD accept partially filled-in FORM and return a new FORM with the remaining fields._

### Server-Side Example

```javascript
// partial submit processing
...
case "POST":
  neededInputs = processForm(suppliedInputs);
  if(neededInputs.length>0) {
    responseBody = generateForm(
      neededInputs, 
      actions["done","cancel","restart","previous"]
    );
  }
  else {
    responseBody = generateResults();
  }
  break
...

```

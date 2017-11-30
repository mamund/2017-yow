## Representor

_You SHOULD implement a message translator[1] to convert internal models into public messages._

### Server-Side Example

```javascript
function representor(object, mimeType, root) {
  var doc;

  // clueless? assume JSON
  if (!mimeType) {
    mimeType = defaultFormat;
  }

  // dispatch to requested representor
  switch (mimeType.toLowerCase()) {
    case "application/vnd.wstl+json":
      doc = wstljson(object, root);
      break;
    case "application/json":
      doc = json(object, root);
      break;
    case "application/vnd.hal+json":
      doc = haljson(object, root);
      break;
    case "application/vnd.siren+json":
      doc = siren(object, root);
      break;  
    case "application/vnd.collection+json":
      doc = cj(object, root);
      break;  
    default:
      doc = cj(object, root);
      break;
  }

  return doc;
}
```

[1] [http://www.enterpriseintegrationpatterns.com/patterns/messaging/MessageTranslator.html](Message Translator)

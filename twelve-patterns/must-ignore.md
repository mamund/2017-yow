## Must Ignore

_Clients MUST IGNORE any data/inputs that the client does not understand._
### Client-Side Handling

```HTML
<script>
  /* incoming responseBody */
  {
     familyName: "Markov",
     givenName: "Shayne",
     dimensione_del_cappello: 12
  }
  ...
</script>

...

<!-- Rendering -->
<ul class="user">
  <li class="familyName">Markov</li>
  <li class="givenName">Shayne</li>
</ul>
```

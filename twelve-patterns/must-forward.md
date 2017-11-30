## Must Forward

_Clients MUST forward (unchanged) any input fields (URL or FORM) that the client does not recognize._

### Client-Side Handling

```HTML
<ul class="user">
  <input type="text" name="familyName" value="Markov" />
  <input type="text" name="givenName" value="Shayne" />
  <input type="text" name="checksum" value="1qw2t3e5rt4u5" />
</ul>

<script>
  ...
  function updateUser() {
    var fields = getInputs(class="user")
    for(var f in fields) {
      switch(f.name) {
        case "familyName":
          f.value="Markus";
          break;
        case "givenName":
          f.value="Ryane";
          break;
      }
    }
    updateForm(fields,class="update");
    updateForm.Send();
  }
  ...
</script>

<form class="update" action="..." method="post">
  <input type="hidden" name="checksum" value="" />
  <input type="text" name="familyName" value="" />
  <input type="text" name="givenName" value="" />
  <input type="submit" />
</form>
```

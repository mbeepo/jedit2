# jedit2
Second version of my Python module that makes it easier to use JSON modules. Now less esoteric!

## The Methods
### load(filename)
Does what it says. It loads the filename you give it and parses it into JSON.


Return type: dict

### add(keys: list, value, filename)
Adds an item to a JSON file. `keys` is the path to the item, and any keys that don't exist will be added.

### append(keys: list, value, filename)
Appends an item to a list in a JSON file. Again, `keys` is the path to the item, but with this method nonexistent keys will not be added.

### edit(keys: list, value, filename)
Edits an item in a JSON file. Just like add, but it doesn't add keys that don't exist.

### remove(keys: list, filename)
Removes the last item of `keys` from the given JSON file.

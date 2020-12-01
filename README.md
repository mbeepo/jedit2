# jedit2
Second version of my Python module that makes it easier to use JSON modules. Now less esoteric!

## Methods
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

## Examples
### file.json
```json
{
	"key1": "value1"
}
```

### load
##### Input
```py
data = jedit2.load("file.json")
print(data)
```
##### Output
```BASH
>> {"key1": "value1"}
```

### add
##### Input
```py
jedit2.add(["key2"], "value2", "file.json")
print(jedit2.load("file.json"))

jedit2.add(["key3", "key4"], [], "file.json"
print(jedit2.load("file.json"))
```
##### Output
```BASH
>> {"key1": "value1", "key2": "value2"}
>> {"key1": "value1", "key2": "value2", "key3": {"key4": []}}
```

### append
##### Input
```py
jedit2.append(["key3", "key4"], "value3", "file.json")
print(jedit2.load("file.json"))
```
##### Output
```BASH
>> {"key1": "value1", "key2": "value2", "key3": {"key4": ["value3"]}}
```

### edit
##### Input
```py
jedit2.edit(["key1"], "value4", "file.json")
print(jedit2.load("file.json"))
```
##### Output
```BASH
>> {"key1": "value4", "key2": "value2", "key3": {"key4": ["value3"]}}
```

### remove
##### Input
```py
jedit2.remove(["key2"], "file.json")
print(jedit2.load("file.json"))
jedit2.remove(["key3", "key4"])
print(jedit2.load("file.json"))
```
##### Output
```BASH
>> {"key1": "value4", "key3": {"key4": ["value3"]}}
>> {"key1": "value4", "key3": {"key4": []}}
```

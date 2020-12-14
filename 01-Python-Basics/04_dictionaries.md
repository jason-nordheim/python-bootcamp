# Dictionaries

A dictionary is an unordered data structure that maps a key value to an object. By storing objects as key-value pairs instead of as a ordered-sequence, objects can be retrieved from a dictionary in constant time.

| Data Structure | Scenario                                                            |
| -------------- | ------------------------------------------------------------------- |
| dictionary     | - quick lookup, without knowing location<br> - order doesn't matter |
| list           | - you need to _sort_ or _order_ items within the data structure     |

## Syntax:

```py
# declaration
my_dict = {'key1': 'value1', 'key2':'value2', 'key3':'value3' }

# adding to a dictionary
# works simply by placing the key in between square bracket
my_dict['key4'] = 'value4'

# there cannot be duplicate keys
# however you can overwrite the value associated with a key
my_dict['key4'] = 'bye bye value4'
print(my_dict['key4']) # => 'bye bye value4'

# lookup
print(my_dict['key`']) # => 'value1'
print(my_dict['value1']) # => KeyError

```

Example:

```py
# dictionary storing prices of a convenience store:
store_prices = {
    'apple': 1.99,
    'pear': 1.89,
    'banana': 0.67,
    'snickers': 0.97,
    'skittles': 0.98,
    'water': 1.99,
    'energy drink': 3.99,
    'coffee': 2.49,
    'newspaper' : 4.99,
    'soda': 2.29
}
```

## Dictionary lookup Complexity

| Operation      | Worst-case | Best-case |
| -------------- | ---------- | --------- |
| Get item by    | θ(n)       | θ(1)      |
| Set item by    | θ(n)       | θ(1)      |
| Delete item by | θ(n)       | θ(1)      |
| Iteration      | θ(n)       | θ(n)      |

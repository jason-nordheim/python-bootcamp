# Lists

Lists are ordered sequences of objects.

- can hold a variety of object types.
- an element in a list can be another list (_this is called a nested list_)
- support **indexing**
- support **slicing**

Syntax: `[element_1, element_2, element3]`

- elements between `[]` (square brackets)
  - `[` denotes the start of the list
  - `]` denotes the end of the list
- each element is delimited by `,` (comma)

```py
# list of numbers
integer_list = [1, 2, 3, 4]
float_list = [98.24, 1.245, 45.35]

# list of strings
letters_list = ['a', 'b', 'c']
names_list = ['Jordan', 'Norman', 'Alejandro']

mixed_list = ['string', 1, 3.145]
```

## Indexing Lists

Elements in a list can be accessed by their index value using `[]` (square bracket) notation (_just like strings_), to obtain the value at a specific index.

Syntax: `list[index]`

- `0` based index

```py
# accessing elements in a list by their index
my_list = ['one', 'two', 'three']
my_list[0] # => 'one'
my_list[1] # => 'two'
```

## Slicing Lists

Elements from a list can be retrieved through **slicing** using the same syntax as slicing a string.

```py
# splicing a list
team_a = ['Scott', 'John', 'Alex', 'Frank', 'Tommy', 'Jordan', 'Brendan']

# get first 5 players
team_a[:5] # => ['Scott', 'John', 'Alex', 'Frank', 'Tommy']

# get last 5 players
team_a[-5:] # => ['Alex', 'Frank', 'Tommy', 'Jordan', 'Brendan']

# get every other player in the list
team_a[::2] # => ['Scott', 'Alex', 'Tommy', 'Brendan']

# get every third player
team_a[::3] # => ['Scott', 'Frank', 'Brendan']
```

> Slicing a list does **not** mutate the list. Slicing a list returns a new list containing only the elements specified.

## Concatenating lists

Concatenating is the process in which a variable is _added_ or _concatenated_ with another variable. Lists in Python can be combined together using the `+` (plus) operator, also called the "addition operator".

Syntax:

```py
list_a = ["one", "two", "three" ] # define one list
list_b = ["four", "five", "six" ] # define a second list
list_c = list_a + list_b  # concatenate the two lists
```

As a result of the operation above `list_c` would equal `['one', 'two', 'three', 'four', 'five', 'six']`.

## Mutating Lists

Lists are **mutable** data structures. Since lists are mutable, their values can be _mutated_ or changed, rather than having to re-assign or replace a variables value.

```py
list_a = ["one", "two", "three" ]

# replace the element at index 0 with the
# uppercase version of the same string
list_a[0] = list_a[0].upper()
print(list_a)
```

Which would produce the output:

```
['ONE', 'two', 'three']
```

### Mutating Methods

There are a variety of methods built into the Python `List` data structure to make it easier to work with lists.

#### The `.append()` method

You can add items to a list using the `append()` method. When invoked, the `append()` method adds the provided object to the **end** of the existing list.

- description
  - adds a new item to the end of a list
- arguments
  - _new_element_ (any type)
- returns
  - `None`

```py
# appending an item to a list

# create a list
team_a = ['Scott', 'John', 'Alex', 'Frank', 'Tommy', 'Jordan', 'Brendan']

# append element to list
team_a.append('Ben')
```

#### The `.pop()` method

The `pop()` is used to remove elements from a list. If the `pop()` method is invoked without any arguments, the **last** item added to the list will be removed from the list. However, if an index position is passed as an argument to `.pop(index)`, the item at the index position specified will be removed from the list.

- description
  - removes an item from a list
  - removes the **last** item added by default.
- arguments
  - `index` : number → (optional) removes item at specified index position
- returns
  - the removed ("popped") element

Since the last element in `team_a` is `'Brendan'`, `team_a.pop()` will remove `'Brendan'` from `team_a`, and return it.

We can store the element that was removed ("popped") from the list using `removed_item = list.pop()`

```py
# removing the last item using pop()
team_a = ['Scott', 'John', 'Alex', 'Frank', 'Tommy', 'Jordan', 'Brendan']

# remove player, store player in `removed_player`
removed_player = team_a.pop()
```

#### The `.sort()` method

The `sort()` method repositions the elements in a list. By default letters will be sorted alphabetically (A-Z), and numbers will be sorted in ascending order (small to large).

- description
  - repositions elements of a List
- arguments
  - `None`
- returns
  - `None` → sorting occurs in-place, no value is returned

```py
letters = ['a', 'c', 'd', 'e' ]
numbers = [10, 8, 59, 92, 10]
```

#### The `.reverse() method

The `reverse()` method repositions the elements in a list such that the order of the elements is reversed from the original position.

- description
  - reverses the order of elements in a list
- arguments
  - `None`
- returns
  - `None`

### Time Complexity of Mutating Lists

| List Method            | Average    | Worst-case |
| ---------------------- | ---------- | ---------- |
| `list.copy()`          | θ(n)       | θ(n)       |
| `list.append(element)` | θ(1)       | θ(1)       |
| `list.pop()`           | θ(1)       | θ(1)       |
| `list.pop(index)`      | θ(n)       | θ(n)       |
| `list.insert(element)` | θ(n)       | θ(n)       |
| `list[index]`          | θ(1)       | θ(1)       |
| `list[index] = value`  | θ(1)       | θ(1)       |
| `list[index] = value`  | θ(1)       | θ(1)       |
| `list.sort()`          | θ(n log n) | θ(n log n) |
| `list.max()`           | θ(n)       | θ(n)       |
| `list.min()`           | θ(n)       | θ(n)       |
| `len(list)`            | θ(n)       | θ(n)       |

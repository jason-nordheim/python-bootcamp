# Variables in Python

Variables allow us to store a value for later use.

Rules

- variable names cannot start with a number
- variable names cannot contain spaces
- variable names cannot use the following symbols: `:`, `"`,`<`, `>`, `|`, `\`, `(`, `)`, `!`, `@`, `#`, `$`, `%`, `^`, `&`, `*`, `~`,`-`, `+`

## Best Practices

- variables names should be lower case
- should avoid any of the reserve words

# Strings

Strings are sequences of characters enclosed in either single or double quotes.

```py
# using single quotes
greeting = 'Hello'

# mixing single and double qoutes
action = "I'm going for a run"
```

Strings are **ordered sequences**, this enables **indexing** and **slicing**, which are both methods of retrieving a sub-section of a string.

## Indexing Strings

Indexing in python uses `[]` (bracket) notation after the string (or variable assigned to a string). Indexing allows you to retrieve a single character from the string.

| character | Index |
| --------- | ----- |
| `h`       | `0`   |
| `e`       | `1`   |
| `l`       | `2`   |
| `l`       | `3`   |
| `o`       | `4`   |

```py
"hello"[1] # => 'e'
"hello"[0] # => 'h'
my_name = "Benjamin Franklin"
my_name[10] # => 'r'
```

## Negative Indexing

Python also supports negative indexing. This allows you to retrieve the reverse index of a string.

> Reverse indexing is the distance from the end of the string denoted as a negative number

| character | Index | Negative Index |
| --------- | ----- | -------------- |
| `h`       | `0`   | `0`            |
| `e`       | `1`   | `-4`           |
| `l`       | `2`   | `-3`           |
| `l`       | `3`   | `-2`           |
| `o`       | `4`   | `-1`           |

```py
my_name = "Benjamin Franklin"
my_name[-1] # => 'n'
my_name[-2] # => 'i'
```

## Slicing

Slicing grabs a _subsection_ of a string, referred to as a "slice".

Syntax: `[start:stop:step]

- `start` index for the start of the slice
- `stop` index to go up to (but not include)
- `step` the size of the jump you take from `start` to `stop`

```py
# sample string to work with
alphabet = 'abcdefghijklmnopqrstuvwxyz'

# slice from index 2, to the end
alphabet[2:] # => 'cdefghijklmnopqrstuvwxyz'

# slice everything up to the index 5 (not including)
alphabet[:5] # => 'abcde'

# slice the middle of string (from index 3 → 7)
alphabet[3:7] # => 'defg'

# slice everything from a string (copy)
alphabet[::] # => 'abcdefghijklmnopqrstuvwxyz'

# slice the entire string, but step by 2
alphabet[::2] # => 'acegikmoqsuwy'

# all together
# slice everything from index 2 → index 15, stepping by 3
alphabet[2:15:3] # => 'cfilo'

# You can also using _slicing_ to reverse a string:
alphabet[::-1] # => 'zyxwvutsrqponmlkjihgfedcba'
```

## String Properties and Methods

### Properties

Strings are **immutable**, meaning that strings cannot be _mutated_ or changed. So if there was a `name` variable set to `"Sam"`
and we attempt to change the `S` to a `P` through mutation, Python would throw `item assignment` error

```py
# create a string
name = "Sam"

# attempt to mutate the string
name[0] = 'P'
```

Error:

```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
```

While mutating the string is **not** possible, it is possible to re-assign a string variable to a new string. So the variable `name` can be changed from `"Sam"` to `"Pam"` by concatenating the string `'P'` with a slice of `name` from index `1` to the end of the string. This is known as **string concatenation**.

```py
name = "Sam"
name = "P" + name[1:] # => 'Pam'
```

## Escape Sequences

Escape sequences are special characters that denote an alternative meeting. Some examples include:

- `\n` new line character
- `\t` tab character

# Numbers

## Integers

## Floating Points

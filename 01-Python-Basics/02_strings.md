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

Be careful when using **string concatenation**, if you try to add to variables together, **both** variables must be strings, or Python will throw a type error.

```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: cannot concatenate 'str' and 'int' objects
```

### Common String Methods

There are a vast amount of string methods to make working with strings in Python easier. Here are some of the most commonly used ones:

### The `upper()` method

Used to get a copy of the string, with every letter converted to uppercase.

```py
greeting = 'Hello World'
greeting.upper() # => 'HELLO WORLD'
```

### The `lower()` method

Used to get a copy of a string in all lowercase

```py
greeting = 'Hello World'
greeting.lower()
# => 'hello world'
```

### The `split()` method

By default, split returns multiple strings (in an list), with each string of the list representing the characters between each section of whitespace.

```py
question = "Hi, how are you today?"
question.split()
#  => ['Hi,', 'how', 'are', 'you', 'today?']
```

However, when `split(char)` is provided a character, `split(char)` will return the source string broken into sections delimited by the provided character

```py
question = "Hi, how are you today?"
question.split('o') # => ['Hi, h', 'w are y', 'u t', 'day?']
```

## String interpolation

String formatting is a way of substituting a value (typically from a variable) into a string. The technical term for this process is known as **string interpolation**.

It can also be thought of as "injecting" a variable into a string. Typically string interpolation is performed to make the output of a variable more readable.

There are multiple ways you can format strings in python.

### The `.format()` method

The format method is called upon a string containing curly braces (e.g. `{}`). The curly braces denote the ordered location that values/variables provided to the `.format()` method will be placed.

Syntax: `string.format(value_a, value_b)`

If no value is placed in the `{}`, the values will be substituted in order.

```py
# default insert
introduction = "My name is {} and I am {} years old"
introduction.format('Suzanne', 17)
# => 'My name is Suzanne and I am 17 years old'
introduction.format('Tara', 18)
# => 'My name is Tara and I am 18 years old'
```

Placing an index inside the `{index}` will return a string with the `{index}` replaced by the corresponding value of the parameter (at the specified index) passed to the `.format()` function

```py
# inserting by index
introduction = "My name is {0} and I am {1} years old"
introduction.format('Suzanne', 17)
# => 'My name is Suzanne and I am 17 years old'
introduction.format('Tara', 18)
# => 'My name is Tara and I am 18 years old'
```

This can be used to repeat value insertions

```py
# index substitution
score_info = '{0} scored {2}/{1} on math and {3}/{1} on english'

score_info.format('Jon', 100, 85, 90)
# => 'Jon scored 85/100 on math and 90/100 on english'
```

Inserted values passed to `.format()` can also be aliased (given a short name) to more easily identify which string will be substituted in each location:

```py
# alias substitution
score_info = '{name} scored {m_score}/{total} on math and {e_score}/{total} on english'

score_info.format(name='Alex', total=100, m_score=74, e_score=92)
# => 'Alex scored 74/100 on math and 92/100 on english'
```

The `.format()` method also supports formatting decimal values (floats) to match a specific format. This can be useful to limit the number of decimal places shown, or pad smaller numbers with `0` so that the output string is consistently the same number of characters.

Syntax: `{value:width.precision f}`

```py
# formating floating point numbers
report_card_a = "{n} - M: {m:3.2f} E: {e:3.2f} S: {s:3.2f}"
report_card_b = "{n} - M: {m:3.0f} E: {e:3.0f} S: {s:3.0f}"

report_card_a.format(n='Jeremy', m=82.567546, e=91.005, s=78.535 )
# => 'Jeremy - M: 82.57 E: 91.00 S: 78.53'
report_card_b.format(n='Jeremy', m=82.567546, e=91.005, s=78.535 )
# => 'Jeremy - M:  83 E:  91 S:  79'
```

### f-strings

Formatted string literals (aka "f-strings") is an alternative method of string interpolation available in newer versions of python (introduced in python 3.6).

Instead of calling the `string.format()` method to perform string interpolation, formatted string literals are created by placing the variable directly in between the `{}` of the formatted string literal definition.

```py
# formatted string literals (f-strings)
student_name = 'Sarah'
introduction = f'Hello, my name is {student_name}'
# => 'Hello, my name is Sarah'

child = 'Joan'
child_age = 4
f'{child} is {child_age} years old'
# => 'Joan is 4 years old'
```

## Escape Sequences

Escape sequences are special characters that denote an alternative meeting. Some examples include:

- `\n` new line character
- `\t` tab character

# The next Step
## Variables

In our code it's often useful to be able to save data and reuse it later without having
to copy and paste or type it all out again. To do this most programming languages have
what are called "variables". A variable is simply a named identifier that we've indicated
should be set to any value we choose. Can you think of a time you noticed a variable being
set while exploring `rps.py`?

Let's take a quick look at variables in `ipython`.

```
In [1]: name = "brodie"

In [2]: print(name)
brodie

In [3]: name = "zak"

In [4]: # what would happen if you ran `print(name)` here?
```

Here we set the variable `name` to have the value `"brodie"`. If we want to print
the variable we only have to refer to the variable, not the value.

## What is a type?

When we left off we had a file, `rps.py`, that we were running. One of the issues we ran
into was when the `rps()` method prompted for input it needed the input to have quotes
around it. What do you think was going on there?

Or, to put the same question a different way: How does the computer know when you've typed
code, and when you've typed data. Consider the following python code snippet:

```python
name = "Zak"
same_name = name
print(name)
print(same_name)
```

What do you think the output of this code snippet will be? If you guessed
```
"Zak"
"Zak"
```

you guessed right, but why? Why isn't it
```
"Zak"
Name
```

The answer is **Types**.

___

In all programming languages we need to differentiate between *our code* and *data*.
We need a way to tell the computer "this value I'm giving you is data, not code".
In order to do this we have to define for a computer exactly what shape data can take.
This definition is a "type". 

The simplest and most common type is an Integer. That is, a whole number that can be 
negative or positive with no decimal. 

```python
var = 12
```

The next most simple type is a Character. That's a single letter. 

```python
var = 'c'
```

And finally, the type that we're confused about now is a String. A string 
is just a group of characters in order. So, the string `"Zak"` is just the 
characters 'Z' and 'a' and 'k' but all bunched together.

```python
var = "Zak"
```

How do we tell the computer "this is a string, not code"? Well, we surround it in
quotes! So in our example

```python
name = "Zak"
same_name = name
print(name)
print(same_name)
```

The computer knows the value of `name` is the string `"Zak"` and knows that we want to
set the value of `same_name` to be the value of `name` which is... `"Zak"`.

### Building vocabulary

When we type a... type into our code and use quotes to indicate it's a string we call
that a **literal**. In fact, Any time we directly type a value into our code it's called
a **literal**. Let's build intuition with the following code snippet.

```python
example1 = 12
example2 = "twelve"
example3 = input("type twelve, please: ")
```

Which variables (`example1`, `example2`, and `example3`) had their values set to **literals**?
If a variable wasn't set to a literal, why not? Where are **all** the literals in this snippet?

Let's build the same intuition with `rps.py`

```python
import time          # includes a library named time
import random        # includes a library named random

def rps():
    """ this plays a game of rock-paper-scissors
        (or a variant of that game ...)
        inputs: no inputs    (prompted text doesn't count as input)
        outputs: no outputs  (printing doesn't count as output)
    """
    name = input('Hi...what is your name? ')
    print()
    print("Hmmm...")
    print()

    if name == 'Eliot' or name == 'Ran':
        print('I\'m "offline" Try later.')
        
    elif name == 'Zach':
        print('Do you mean Jeff?')
        time.sleep(1)
        print('No?')
        time.sleep(1)
        print('Oh.')
        
    else:
        print('Welcome,', name)
        my_choice = random.choice(['rock','paper','scissors'])
        print('By the way, I choose ', my_choice)
```

Where do you see a literal, and where do we use a variable?

## Final intuition building

Here are some questions for you to explore and answer.

What do you think would happen if you tried to write the code
```python
"name" = brodie
```

Does this code even make sense? Why or why not?

In `rps.py` is there anywhere where it would be literally impossible to use a literal and
get the functionality we want out of it?

## A challenging challenge

Let's edit `rps.py`. Delete **everything** in that file and paste this new code instead.
```python
import random          # imports the library named random

def rps():
    """ this plays a game of rock-paper-scissors
        (or a variant of that game)
        arguments: no arguments    (prompted text doesn't count as an argument)
        results: no results        (printing doesn't count as a result)
    """
    user = input("Choose your weapon: ")
    comp = random.choice(['rock','paper','scissors'])
    print()

    print('The user (you)   chose', user)
    print('The computer (I) chose', comp)
    print()

    if user == 'rock':
        print('Ha! I really chose paper--I WIN!')

    print("Better luck next time...")
```

Before running the code see if you can figure out what this program will do. Here is a hint:
it's the beginning of a Rock, Paper, Scissors game. Does it work correctly? Can you see what
the issue is?

### The tools you'll need

It's time to break out some new tools. The fundamental building blocks of all programs are
**control flow** and **comparisons**. **Control flow** means **reserved words** that tell the
langauge whether or not a specific line of your code should run. **Comparisons** help you
look at two values and understand how they relate to each other.

#### Control Flow

In our new `rps.py` an example of a **control flow** statement is
```python
if user == 'rock':
    print('Ha! I really chose paper--I WIN!')
```

the line of code `print('Ha! I really chose paper--I WIN!')` will only run **if**
the value of the `user` variable (where was that set?) is exactly the string `'rock'`
(for now we're going to ignore the difference between `'` and `"` and use them
interchangeably).

After an `if:` statement all your code must be one tab indented so that Python
knows what belongs to the `if:` and what does not.

You can also write `else:` **at the same indentation as a previously declared `if:`**.
Doing so will **only** execute the code indented below the `else:` if the comparison
made by the `if:` is **not** true.

Finally, you can write `elif [comparison]:`. This marks code to be run **exclusively**
when the comparison is true **and** no previous `if:` or `elif:` statements have been
true.

#### Comparisons

Comparisons always take the form of `[var or lit] [operator] [var or lit]`.
Let's consider our new `rps.py` example: `user == 'rock'`. First we have a
variable. We then use the `==` (equalivance) operator. Then we have a literal.

Using a comparison operator will *return* a new **type**. This type is a **boolean**
and is always one of two possible values. In Python all Booleans will **always* be either
`True` or `False`. Boolean literals are the words, without quotes, `True` or `False` and
must begin with a capital letter.

Play around with booleans in `ipython`.
```
In [1]: True == False
Out[1]: False

In [2]: True == True
Out[2]: True

In [3]: "zak" == "zak"
Out[3]: True

In [4]: "Zak" == "zak"
Out[4]: False
```

#### Back to the challenging challenge

Using what we've now learned about Control Flow, Comparisons, and Booleans
can you fix our new `rps.py` so that it plays a correct game of Rock, Paper,
Scissors and correctly identifies when it has won or lost?


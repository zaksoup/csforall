# Welcome to Python
## Let's talk about programming languages
All programming languages have the same basic building blocks.

* Syntax:

  The actual form of the language.
* Semantics
  
  The actual meaning of the code you write (as opposed to the form it is in)

* Data structure
  
  How you represent values
  
## What does this have to do with Python?
Python's syntax is made up of **Identifiers** and **Reserved Words**. Let's look at the difference in action!

```python
import random

def hello_world():
    greeting = random.choice(['world', 'friend', 'there'])
    print('hello', greeting)
```

Identifiers can be created at any point by the author of a program.
Reserved words always mean a specific thing for a language.
In this case, the `def` Reserved Word always precedes an Identifier that will be
the name of a function.

In the code example above can you think of which parts are Reserved Words and which parts are Identifiers?

___

The answer is a bit of a trick question.
The only reserved words you see above are `def` and `import`.
`random` is the name of a library and is therefor an identifier. The author of the 
library could have used any name, but chose `random`.
Similarly, `print` is a function provided by the "standard library" of the language,
but isn't a Reserved Word that you use to control how the language actually works.
`greeting` is a variable, defined by the author (we'll talk more about variables later).

So how can we think about the difference between Reserved Words and Identifiers?
Identifiers are Your Code. I like to think of Reserved words like quotes and questions marks
in written english. The sentence "I'm friends with some communists, Ash, and Brodie" might
imply that Ash and Brodie aren't communists, whereas if I remove a comma ("I'm friends with some
communists, Ash and Brodie") it makes it clear that Ash and Brodie are **definitely** communists.
Even though both sentences have the same words (Identifiers), their meaning changes with punctuation
(Reserved Words).

___

Let's look at a longer python file. Save this in your project as `rps.py`.

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

In `ipython` you'll notice if you run this file there's no output.
That's because this file only **defines** a method. To actually run the code
you'll have to call the method directly.

```
In [1]: run rps.py

In [2]: rps()
Hi...what is your name? Zach

Hmmm...

Do you mean Jeff?
No?
Oh.

In [3]:
```

Your project is to play around with `rps.py`. Can you determine which parts
of the code you've been given are Reserved Words and built into the langauge?
What about which parts are Identifiers and created by the author to actually 
make up the functionality of the program. What happens if you change the code
and break something? Can you understand the error the `ipython` gives you and
fix the issue?

Try this:
* To see how Python handles errors, remove one of the two equals signs in the `elif` line
  * so that the line reads `elif name = 'Zach':`
  * Then, try to re-looad the file with `run rps.py`
  * Python will tell you there is a "syntax error" and give you a chance to fix it. 

Good luck!

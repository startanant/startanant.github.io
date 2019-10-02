---
layout: post
title:  "A needle in a haystack: Part II"
date:   2019-09-30 17:33:46 -0400
categories: tech
tags: python javascript programming
---

**Note**: If you're new to this series, start with the [first post]({% post_url 2019-09-25-find-needle-1 %}) in the series for the sake of continuity.

In the previous scenario, we looked for a letter in a word. Now, let's take it a step further and look for words in a sentence. You'll see that the needle and haystack we discussed earlier, get a lot larger and complicated in this one (not nearly large enough to make it any easier to find the needle, though).

The needle is now an array of words, as is the haystack. To complicate things further, the output will also be - you guessed it - an array of words (plus a counter), as opposed to just being a boolean value of true or false.

We used JavaScript to explain the previous scenario. While we can continue using JavaScript for this scenrio too, let's use Python this time, so that we can demonstrate our abilities as polyglots.

Here's the code for this scenario. You might find it a bit daunting at first but we'll break it down together.

```python
import re
import sys

def findNeedles(haystack, needles):
  if len(needles) > 5:
    sys.stderr.write('Too many words!')
  else:
    countArray = [0]*len(needles)
    words = re.split("[ \"\'\t\n\b\f\r]", haystack)
    for i in range(len(needles)):
      for j in range(len(words)):
        if needles[i] == words[j]:
         countArray[i] += 1
    for j in range(len(needles)):
        print (needles[j] + ": " + str(countArray[j]))
		
haystack = "The quick brown dog jumped over the lazy dog"
needles = ['The', 'fox', 'dog']

print "Haystack = ", haystack
print "Needles = ", needles
findNeedles(haystack, needles)
```


Save the above program to a file (let's call it `find-needles.py`).

But, before we run the program and arrive at the output, let's go over some of the Python modules, functions and programming constructs we have used in our code.

**Import**: The Python code in one module gains access to the code in another module, by the process of importing it. The import statement combines two operations; first it searches for the named module, then it binds the results of that search to a name in the local scope. 
For more information, see [https://docs.python.org/3/reference/import.html](https://docs.python.org/3/reference/import.html)

In our scenario, `import re` searches for the regular expression module and allows access to functions and attributes available in the `re` module, in the local scope.


**Regular Expressions**: A regular expression specifies a set of strings that matches it; the functions in this module let you check if a particular string matches a given regular expression (or if a given regular expression matches a particular string, which comes down to the same thing).
For more information, see [https://docs.python.org/3/library/re.html](https://docs.python.org/3/library/re.html)

`re.split(pattern, string)`

Here, the `split` method available in the `re` module breaks up the `string` by the occurrences of `pattern` and returns a list as shown below.

```python
>>> re.split("[ \"\'\t\n\b\f\r]", "she sells sea shells")
['she', 'sells', 'sea', 'shells']
```
Try to figure out what this pattern is doing by running the above code in the Python interpreter. We will cover regular expressions in more detail in a future post. Stay tuned.

**Range**: When you call the `range` function with one argument, it returns a sequence of numbers that starts at 0 and includes every whole number up to, but not including, the number you have provided as the argument.
For more information, see [https://docs.python.org/3/library/stdtypes.html#typesseq-range](https://docs.python.org/3/library/stdtypes.html#typesseq-range)


`range(x)`

where, x is the number provided as the argument.

```python
>>> range(5)
[0, 1, 2, 3, 4]
```

**Nested For loops** : 

```
for i in range(len(needles)):
      for j in range(len(words)):
      	line 1
      	line 2
```

During the first pass, for a given value of i assigned in the outer loop, the control passes to the inner loop,  which loops through lines 1,2.. etc to completion as many number of times for every value of j, while the value of i remains constant. The value of i changes in the next pass.


Okay. That much information should work for now. I'd rather not hand you the solution on a platter. Please write to me if you have any questions.

Let's get back to our program.
Run `find-needles.py` from the terminal.

```python
$ python find-needles.py
Haystack =  The quick brown dog jumped over the lazy dog
Needles =  ['The', 'fox', 'dog']
The: 1
fox: 0
dog: 2
```

The output returned by the program is a list of needles (words), plus the number of occurrences of each needle (word), which we found in our haystack (sentence). We have successfully upgraded our pursuit of needles to match the increased complexity of the haystack.

Next time, we will find some more needles from another haystack; and maybe use a different language again.

---
title       : Basic String Manipulation
description : In this chapter you will learn some basic techniques to deal with string objects. These include finding the length of the string, indexing the string, finding and changing part of the string, and formatting the string. They will give you a head start in text mining, so let's practice!  
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:VideoExercise lang:python xp:50 skills:2 key:ef6777fad5
## Getting to know your string
- length of string: len(s)
- string index: s[2]
- find part of string: s.find(string) return index or -1
- split a string: s.split(string) split by space by default
- join a string: s.join(string)

--- type:NormalExercise lang:python xp:50 skills:1 key:8c8181cc6b
## Finding the length of a string and indexing it

A website named ["The Dictionary of Obscure Sorrows"](http://www.dictionaryofobscuresorrows.com/) has been dedicated to making up words that describe the emotions that we all feel, but fail to communicate. In this course, we will use some entries on "The Dictionary of Obscure Sorrows" as examples.

One of the most famous words from this dictionary is "sonder," the realization that each passerby has a life as vivid and complex as your own. Imagine that this word has just been created and you need to teach Python, never having encountered "sonder" before, to learn to recognize it by its length and the values in its 5th and 3rd-last characters. Use the techniques shown in the video to do that

*** =instructions
- Find the length of "sonder." The syntax of Python's built-in function `len` is `len(s)` where `s` is a string.
- Find the 5th character in "sonder." The syntax of the string object's operator `[ ]` is `s[n]` where `n` represents the index.
- Find the 3rd-last character in "sonder," also using `[ ]`.

*** =hint
- You should call the command `len(s)` to create `l`.
- Remember that we count index starting from 0. So if you want to find the 5th character you should use `[n]`.
- When we want to find characters from the end of the word, we add a `-` sign before the index, starting from `-1`.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Assign "sonder" to the object s
s = "sonder"

# Find the length of s: l


# Find the 5th character of s: char_5


# Find the 3rd-last character of s: char_3_last


# Print out the result
print(l, char_5, char_3_last)

```

*** =solution
```{python}
# Assign "sonder" to the object s
s = "sonder"

# Find the length of s: l
l = len(s)

# Find the 5th character of s: char_5
char_5 = s[4]

# Find the 3rd-last character of s: char_3_last
char_3_last = s[-3]

# Print out the result
print(l, char_5, char_3_last)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:50 skills:1 key:514818b19a
## Slice Strings

A particular long word on "The Dictionary of Obscure Sorrows" is Ruckkehrunruhe, which refers to "the feeling of returning home after an immersive trip only to find it fading rapidly from your awareness." Say you want to slice this word at every occurence of the character "r", and turn it to ["uckkeh", "un", "uhe"]. Use `split` to accompanish that.

*** =instructions
- Use `split` to slice the word "Ruckkehrunruhe" at every occurence of "r." The syntax of the string object's built-in method `split` is `s.split(string)` where `s` is the string you want to split and `string` is the delimiter string.

*** =hint
- You should call `s.split("r")` to create `lst`.

*** =pre_exercise_code
```{python}


```

*** =sample_code
```{python}
# Assign Ruckkehrunruhe to the object s
s = "Ruckkehrunruhe"

# Slice the word at every occurence of r: lst


# Print out the resulting list
print(lst)

```

*** =solution
```{python}
# Assign Ruckkehrunruhe to the object s
s = "Ruckkehrunruhe"

# Slice the word at every occurence of r: lst
lst = s.split("r")

# Print out the resulting list
print(lst)
```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:3319f86744
## Split Lines and Print on New Lines

With the `split` method, you can also split a paragraph that has several sentences, and print them each on a new line. To do it, you can first break the paragraph into a list of each sentence using `.` as a delimiter. Then print out each sentence, ending with `\n` which in Python signifies starting a new line.

*** =instructions
- Use `split` to slice the definition of the word "Ruckkehrunruhe" at every occurence of "."
- Iterate over the list you get and add `\n` to each sentence.

*** =hint
- The syntax for `split` is `s.split(string)`, where `s` is the string you want to split and `string` is the delimiter string.
- Use a for loop to print out every sentence of the list.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Assign the definition of "Ruckkehrunruhe" to the object par
par = "Try! Try! See!"

# Slice the word at every occurence of "!": lst


# Print out each sentence ending with \n



```

*** =solution
```{python}
# Assign the definition of "Ruckkehrunruhe" to the object par
par = "Try! Try! See!"

# Slice the word at every occurence of "!": lst
lst = par.split("!")

# Print out each sentence ending with \n
for snt in lst:
    print(snt+"\n")

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

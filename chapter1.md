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
- Find the 5th character in "sonder." The syntax of the string object's operator "[]" is `s[n]` where `n` represents the index.
- Find the 3rd-last character in "sonder," also using "[]."

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
char_5 = s[-3]

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:8b77a2e72b
## Slice Strings

A particular long word on "The Dictionary of Obscure Sorrows" is Rückkehrunruhe, which refers to "the feeling of returning home after an immersive trip only to find it fading rapidly from your awareness." Say you want to slice this word at every occurence of the character "r", and turn it to ["ückkeh", "un", "uhe"]. Use `split` to accompanish that.

*** =instructions
- Use `split` to slice the word "Rückkehrunruhe" at every occurence of "r." The syntax of the string object's built-in method `split` is `s.split(string)` where `s` is the string you want to split and `string` is the delimiter string.

*** =hint
- You should call `s.split("r")` to create `lst`.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Assign "Rückkehrunruhe" to the object s
s = "sonder"

# Slice the word at every occurence of r: lst


```

*** =solution
```{python}
# Assign "Rückkehrunruhe" to the object s
s = "sonder"

# Slice the word at every occurence of r: lst
lst = s.slice("r")

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

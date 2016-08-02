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
## Join Strings

Another method we often use on strings is `join` which, as the name suggests, is the opposite of `split`. `s.join(lst)` adds the string `s` after each string in the list `lst`. For instance, in the previous example, after slicing the "Ruckkehrunruhe" with "r", we got three fragments of the word. We can use `join` to add "h" to the end of each fragment and create a new word.  

*** =instructions
- Use `join` to add "h" to the end of each fragment in the list `lst`.

*** =hint
- Use `join` on "." and take `lst` as the argument.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Assign the fragements of "Ruckkehrunruhe" to the object lst
lst = ["uckkeh","un","uhe"]

# Join the "h" at the end of each word in lst: s2


# Print out each sentence ending with \n


```

*** =solution
```{python}
# Assign the fragements of "Ruckkehrunruhe" to the object lst
lst = ["uckkeh","un","uhe"]

# Join the "h" at the end of each word in lst: s2


# Print out each sentence ending with \n


```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:1723f19db3
## Capitalize First Letters

Sometimes you get a paragraph of text where the first letter of each sentence is not capitalized. The method `capitalize()` can Capitalize the first letter of the whole string, but there are multiple sentences in a string, it only takes care of the first sentence. What can we do? Yes, you guessed it. We can use `split` to divide the paragraph into its sentences, use `capitalize()` to capitalize the first letter in each sentence, and then join all the individual sentences together!

Note that `s.capitalize` creates a new string whose first letter is capitalized, and the original `s` will remain unchanged. You have to deal with that.

*** =instructions
- Use `split` to slice the definition of the word "Ruckkehrunruhe" (edited for training purpose) at every occurence of ".".
- Iterate over the sentences and change it to a new string created by `capitalize()`.
- Join all the sentences back together with ".".

*** =hint
- The syntax for `split` is `s.split(string)`, where `s` is the string you want to split and `string` is the delimiter string.
- Use a for loop to go through every sentence.
- The syntax for `join` is `s.join(lst)`, where `s` is the string to put at the end of each string in `lst`.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Assign the definition of "Ruckkehrunruhe" to the object par
par = "ruckkehrunruhe is the feeling of returning home after an immersive trip only to find it fading rapidly from your awareness. you have to keep reminding yourself that it happened at all. however it felt so vivid just days ago."

# Slice the word at every occurence of ".": lst


# Capitalize the first letter of each sentence




# Joining all the sentences back together


# Print the result
print(lst)

```

*** =solution
```{python}
# Assign the definition of "Ruckkehrunruhe" to the object par
par = "ruckkehrunruhe is the feeling of returning home after an immersive trip only to find it fading rapidly from your awareness. you have to keep reminding yourself that it happened at all. however it felt so vivid just days ago."

# Slice the word at every occurence of ".": lst
lst = par.split(".")

# Capitalize the first letter of each sentence
for snt in lst:
    snt = snt.capitalize()

# Joining all the sentences back together
".".join(lst)

# Print the result
print(lst)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

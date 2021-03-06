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

One of the most famous words from this dictionary is "sonder," the realization that each passerby has a life as vivid and complex as your own. Imagine that this word has just been created and you need to teach Python, never having encountered "sonder" before, to learn to recognize it by its length and the values in its 5th and 3rd-last characters. Use the techniques shown in the video to do that.

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
## Slicing strings

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
## Joining strings

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
## Capitalizing first letters

Sometimes you get a paragraph of text where the first letter of each sentence is not capitalized. The method `capitalize()` can Capitalize the first letter of the whole string, but there are multiple sentences in a string, it only takes care of the first sentence. What can we do? Yes, you guessed it. We can use `split` to divide the paragraph into its sentences, use `capitalize()` to capitalize the first letter in each sentence, and then join all the individual sentences together!

Note that `join()` and `capitalize()` create a new string without changing the original ones. So you will have to explicitly assign the old string or list of strings to new ones.

*** =instructions
- Use `split` to slice the definition of the word "Ruckkehrunruhe" (edited for training purpose) at every occurence of ". ". Remember you want to include the space after each period in the delimiter!
- Iterate over all the sentences and change them to new strings created by `capitalize()`.
- Join all the sentences back together with ". ".

*** =hint
- The syntax for `split` is `s.split(string)`, where `s` is the string you want to split and `string` is the delimiter string.
- Use its index to iterate over each element in `lst`, and assign the capitalized string to the element.
- The syntax for `join` is `s.join(lst)`, where `s` is the string to put at the end of each string in `lst`.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Assign the definition of "Ruckkehrunruhe" to the object par
par = "ruckkehrunruhe is the feeling of returning home after an immersive trip only to find it fading rapidly from your awareness. you have to keep reminding yourself that it happened at all. however it felt so vivid just days ago."

# Slice the word at every occurence of ". ": lst


# Create an empty list to store the sentences with capitalized first letter: lst_cap
lst_cap = []

# Capitalize the first letter of each sentence and append it to lst_cap




# Joining all the sentences back together: par_cap


# Print the result
print(par_cap)

```

*** =solution
```{python}
# Assign the definition of "Ruckkehrunruhe" to the object par
par = "ruckkehrunruhe is the feeling of returning home after an immersive trip only to find it fading rapidly from your awareness. you have to keep reminding yourself that it happened at all. however it felt so vivid just days ago."

# Slice the word at every occurence of ". ": lst
lst = par.split(". ")

# Create an empty list to store the sentences with capitalized first letter: lst_cap
lst_cap = []

# Capitalize the first letter of each sentence and append it to lst_cap
for i in range(len(lst)):
    lst_cap.append(lst[i].capitalize())

# Joining all the sentences back together: par_cap
par_cap = ". ".join(lst_cap)

# Print the result
print(par_cap)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```


--- type:MultipleChoiceExercise lang:python xp:100 skills:1 key:3e74f114a8
## Displaying Text after Tagline

You received a string that contains a text message you want to collect, but it also contains information about the text, separated from the actual content with ">>>START_HERE<<<". Enter "text" in the IPython Shell to see the full string. Which of the following codes can help you create an object `text_clean` that has only the text message?


*** =instructions
- `text_clean = text.split(">>>START_HERE<<<")`
- `lst = text.split(">>>START_HERE<<<")``
  `text_clean = lst[1]`
- `text_clean = text.split(">>>START_HERE<<<")[2]`

*** =hint
- Recall what kind of object `split` outputs.

*** =pre_exercise_code
```{python}
text="Time:17:06Jul07 Location:Cambridge,MA >>START_HERE<< Do you want to grab dinner?"

```

*** =sct
```{python}
msg1 = """`split` generates a list of strings, not just a single string."""

msg2 = """Yes!"""

msg3 = """This code is correct except that the index in a list starts with 0."""

test_mc(2, [msg1, msg2, msg3])
```

--- type:VideoExercise lang:python xp:50 skills:2 key:40f8c6581f
## Replacing and Stripping
- replace: str.replace(old_string, new_strin, count)
- strip: str.strip(string)


--- type:NormalExercise lang:python xp:100 skills:1 key:e115d724c0
## Replacing Part of a String with Another String

Charles Dickens's novel "The Tale of the Two Cities" famously begins with the line:"It was the best of times; it was the worst of times; it was the age of wisdom; it was the age of foolishness; it was the epoch of belief; it was the epoch of incredulity." Now, try to use `replace` to change "was" in this sentence to "is." Remember that the syntax of `replace` is `str.replace(old_string,new_string)`.

*** =instructions
- Use `replace` to change "was" to "is" in the string `text`.

*** =hint
- Use the method `replace` on `text` and take the old string and the new string as arguments.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Assign the opening of "The Tale of Two Cities" to the object text
text = "It was the best of times; it was the worst of times; it was the age of wisdom; it was the age of foolishness; it was the epoch of belief; it was the epoch of incredulity."

# Replace every occurence of "was" with "is": new_text


# Print out the resulting string
print(new_text)

```

*** =solution
```{python}
# Assign the opening of "The Tale of Two Cities" to the object text
text = "It was the best of times; it was the worst of times; it was the age of wisdom; it was the age of foolishness; it was the epoch of belief; it was the epoch of incredulity."

# Replace every occurence of "was" with "is": new_text
new_text = text.replace("was","is")

# Print out the resulting string
print(new_text)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```



--- type:NormalExercise lang:python xp:100 skills:1 key:c91a8bede7
## Replacing String with a Count

Say you think that the line "It was the best of times; it was the worst of times" doesn't represent how you feel: We have already been through the worst of times, and now it's just the best of times. Thus, you want to change the first "was" to "is" but keep the second one. You can do that by adding a count as an argument after the old and new string.

*** =instructions
- Use `replace` to change "was" to "is" with a count of 1.

*** =hint
- The syntax for `replace` is `str.replace(old_string, new_string, count)`.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Assign the first line of "The Tale of Two Cities" to the object text
text = "It was the best of times; it was the worst of times."

# Replace only the first occurence of "was" with "is": new_text


# Print out the resulting string
print(new_text)

```

*** =solution
```{python}
# Assign the first line of "The Tale of Two Cities" to the object text
text = "It was the best of times; it was the worst of times."

# Replace only the first occurence of "was" with "is": new_text
new_text = text.replace("was","is",1)

# Print out the resulting string
print(new_text)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:6569731b94
## Strip Away a New Line

We have a damaged digital file of "The Tale of Two Cities," where the opening is mixed with "0"s at the beginning and end. Try to get rid of these "0"s using `strip`. Remember the basic syntax of "0" is `str.strip(string)`

*** =instructions
- Use `strip` to delete `0` from `text`.

*** =hint
- Use `strip` on `text` to generate a new text.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Assign the opening of "The Tale of Two Cities" to the object text
text = "00000It was the best of times; it was the worst of times; it was the age of wisdom; it was the age of foolishness; it was the epoch of b0elief; it was the epoch of incredulity.0000"

# Strip the 0s away from the text: new_text


# Print out the resulting string
print(new_text)

```

*** =solution
```{python}
# Assign the opening of "The Tale of Two Cities" to the object text
text = "00000It was the best of times; it was the worst of times; it was the age of wisdom; it was the age of foolishness; it was the epoch of b0elief; it was the epoch of incredulity.0000"

# Strip the 0s away from the text: new_text
new_text = text.strip("0")

# Print out the resulting string
print(new_text)


```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```
--- type:MultipleChoiceExercise lang:python xp:100 skills:1 key:16955fff5b
## Stripping and Replacing

A coder starts with an object `string` whose content is "06x008600", and did the following actions to it:

`string_1 = string.strip("0")`
`string_2 = string_1.replace("6","60")`
`string_3 = string_2.strip("0")`

What will `string_3` be?

*** =instructions
- 6x0086
- 060x00860
- 60x00860
- 60x0086

*** =hint
- Recall what `replace` and `strip` each do.

*** =pre_exercise_code
```{python}

```

*** =sct
```{python}
msg1 = """This will be the content of `stirng_1`."""

msg2 = """Think more carefully."""

msg3 = """This will be the content of `string_2`."""

msg4 = """Exactly!"""

test_mc(4, [msg1, msg2, msg3, msg4])
```



--- type:NormalExercise lang:python xp:100 skills:1 key:3f0171461c
## Stripping Away a New Line

We have a damaged digital file of "The Tale of Two Cities," where the opening is mixed with "0"s at the beginning and end. Try to get rid of these "0"s using `strip`. Remember the basic syntax of "0" is `str.strip(string)`

*** =instructions
- Use `strip` to delete `0` from `text`.

*** =hint
- Use `strip` on `text` to generate a new text.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Assign the opening of "The Tale of Two Cities" to the object text
text = "00000It was the best of times; it was the worst of times; it was the age of wisdom; it was the age of foolishness; it was the epoch of b0elief; it was the epoch of incredulity.0000"

# Strip the 0s away from the text: new_text


# Print out the resulting string
print(new_text)

```

*** =solution
```{python}
# Assign the opening of "The Tale of Two Cities" to the object text
text = "00000It was the best of times; it was the worst of times; it was the age of wisdom; it was the age of foolishness; it was the epoch of b0elief; it was the epoch of incredulity.0000"

# Strip the 0s away from the text: new_text
new_text = text.strip("0")

# Print out the resulting string
print(new_text)


```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

*The description of the part about format is a bit too vague. Can't figure out exactly what I'm supposed to teach the student because there's a lot you can do with `format()`*

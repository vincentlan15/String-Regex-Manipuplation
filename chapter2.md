---
title       : Regular Expressions
description : When we talked about `replace` in last chapter, we had to input the exact text as an argument. However, in many cases, we want to search or replace a pattern, things like "words that begin with 'r'" or "strings that have a parenthesis in it." For these tasks, we would need regular expressions.

attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:VideoExercise lang:python xp:50 skills:2 key:ef6777fad5
## What are regular expressions?
- match on characters
- match begin of line
- match end of line
- match wildcard
- match specific type of characters
- re.match
- re.findall()

--- type:NormalExercise lang:python xp:50 skills:1 key:8c8181cc6b
## Searching for a sequence of string

Biologists often need to look at sequences of nucleotides within a DNA molecule to determine the properties and function of the DNA. Quite often though, these sequences can be very long and seemingly random, and a search using regular expressions can be helpful. In this exercise, use `re.search()` to help a biologist find out if the pattern "AGA" exists in a sequence he is working on.

*** =instructions
- Import the regular expression package `re`.
- Use `re.search()` to find "AGA" in the sequence `seq`.
- Print out the `results`.

*** =hint
- The command to import package x is `import x`.
- The basic syntax of `re.search` is `re.search(pattern, string)`.
- You don't need to change the code for the `print` statement that we provided.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Import re


# Assign the sequence to the object seq
seq = "ATGCTTCGGCAAGACTCAAAAAATA"

# Search for AGA: results


# Print out the results
print(____)


```

*** =solution
```{python}
# Import re
import re

# Assign the sequence to the object seq
seq = "ATGCTTCGGCAAGACTCAAAAAATA"

# Search for AGA: results
results = re.search("AGA", seq)

# Print out the result
print(results)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:50 skills:1 key:514818b19a
## Searching for a period

Now you want to know if the opening of "A Tale of Two Cities" has a complete sentence that ends with the letter "es" and then a period. Use `re.search()` and the regular expression of "es." to find out!

*** =instructions
- Import the `re` package.
- Use `re.search()` to check if there is "es." in the object `text`.
- Print out the `results`.
- Click `Submit Answer` to print out the original `text` to see for yourself if there's any period.  

*** =hint
- The command to import package `x` is `import x`.
- The regular expression for period is `\.`.
- You don't need to change the code we provided for the first `print` statement.
- You don't need to change the code for the second `print` statement.

*** =pre_exercise_code
```{python}
text = "It was the best of times, it was the worst of times, it was the age of wisdom, it was the age of foolishness, it was the epoch of belief, it was the epoch of incredulity..."

```

*** =sample_code
```{python}
# Import re


# Search for the regular expression of es. in text: results


# Print out the results
print()

# Print out the original text
print(text)

```

*** =solution
```{python}
# Import re
import re

# Search for the regular expression of es. in text: results
results = re.search("es/.", text)

# Print out the results
print(results)

# Print out the original text
print(text)

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
## Replace and Strip
- replace: str.replace(old_string, new_strin, count)
- strip: str.strip(string)


--- type:NormalExercise lang:python xp:100 skills:1 key:e115d724c0
## Replace Part of a String with Another String

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
## Replace String with a Count

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
## Strip and Replace

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


--- type:VideoExercise lang:python xp:50 skills:2 key:d46e7bc1da
## Replace and Strip
- replace: str.replace(old_string, new_strin, count)
- strip: str.strip(string)


--- type:NormalExercise lang:python xp:100 skills:1 key:536588d87c
## Replace Part of a String with Another String

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



*The description of the part about format is a bit too vague. Can't figure out exactly what I'm supposed to teach the student because there's a lot you can do with `format()`*

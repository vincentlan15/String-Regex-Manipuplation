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
## Searching for a sentence ending

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
print(____)

# Print out the original text
print(____)

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
## Find all

Now you are simply interested in finding "es", no matter if they are followed by a period or not. You know they have to be in the `text`, because "times" already have "es." However, you want to know if there are more occurences of this pattern, so you want to use `re.findall()` to saarch for all `es` in the `text`.    

*** =instructions
- Use `re.findall()` to find all `es` in the `text`.

*** =hint
- The syntax for `re.findall()` is `re.findall(pattern, string)`.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Import re
import re

# Find all `es` in `text`: results


# Print the results
print(____)

```

*** =solution
```{python}
# Import re
import re

# Find all `es` in `text`: results
results = re.findall("es", text)

# Print the results
print(results)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:1723f19db3
## Match characters at beginning and end

What if you want to search for characters only at the beginning or ending of a text? The go-to tool of such tasks is `re.match()`. which by default searches for a pattern only at the beginning of a string. Now, find out if the DNA sequence you worked with earlier starts with "ATG."

*** =instructions
- Use `match` to find out if the DNA sequence `seq` start with "ATG".
- Print out the results.

*** =hint
- The syntax for `match` is `re.match(pattern, string)`.
- You don't need to change the code for the print statement that we have provided.

*** =pre_exercise_code
```{python}
seq = "ATGCTTCGGCAAGACTCAAAAAATA"
```

*** =sample_code
```{python}
# Import re
import re

# Match ATG at the beginning of seq: results


# Print out the results
print(____)

```

*** =solution
```{python}
# Import re
import re

# Match ATG at the beginning of seq: results
results = re.match("ATG",seq)

# Print out the results
print(results)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```


--- type:MultipleChoiceExercise lang:python xp:100 skills:1 key:3e74f114a8
## From Regular Expression to String

What string does the following regular expression correspond to?
`"Let's\s+dance\."\s+he\s+said\s+\(looking\s+me\s+in\s+the\s+eye\)\.`

*** =instructions
- Let's\s dance. s\hes saids lookings mes ins thes eye. 
- Let's dance. he said looking me in the eye.
- "Let's dance."he said(looking me in the eye).
- "Let's dance." he said (looking me in the eye).

*** =hint
- Recall what `\s`, and `+` mean.

*** =pre_exercise_code
```{python}
text="Time:17:06Jul07 Location:Cambridge,MA >>START_HERE<< Do you want to grab dinner?"

```

*** =sct
```{python}
msg1 = """`\s+` means space. It is not related to the letter `s`."""

msg2 = """Pay attention to `\"`, `\(` and other expressions for punctuations."""

msg3 = """Pay attention to all the `\s+` that signifies a space."""

msg4 = """Exactly!"""


test_mc(4, [msg1, msg2, msg3, msg4])
```

--- type:VideoExercise lang:python xp:50 skills:2 key:40f8c6581f
## Search with Pattern(??)
- |: search for either 
- []: any of the characters
- \\: this is not re!

--- type:NormalExercise lang:python xp:100 skills:1 key:e115d724c0
## Search for either words

The opening of "A Tale of Two Cities," which you are very familiar by now, has many pairs of antonyms. You want to know if Dickens used "wisdom" and "stupidity" as one of these pairs, but you are cautious that he might have used another antonym of "wisdom" or of "stupidity." Thus, you determine to check if either of them appears in the text. Use `|` to do that.

*** =instructions
- Use `|` to find if either "wisdom" or "stupidity" is in the string `text`.

*** =hint
- Use `re.search` and put `|` in the argument.

*** =pre_exercise_code
```{python}
text = "It was the best of times, it was the worst of times, it was the age of wisdom, it was the age of foolishness, it was the epoch of belief, it was the epoch of incredulity..."

```

*** =sample_code
```{python}
# Import re
import re

# Search for wisdom and stupidity in text: results


# Print the results
print(____)

# Print the text to check if the results are correct
print(____)

```

*** =solution
```{python}
# Import re
import re

# Search for wisdom and stupidity in text: results
results = re.search("wisdom|stupidity", text)

# Print the results
print(results)

# Print the text to check if the results are correct
print(text)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```



--- type:NormalExercise lang:python xp:100 skills:1 key:c91a8bede7
## Search for a Group of Characters

You love every letter in the alphabet table from "t" to "x". You want to know if your favorite passage, the opening of "A Tale of Two Cities," has any of these letters using `[]`. One way to do it is search for `[tuvwx]`. Another is to search `[t-x]`, which will tell Python to search for any letter from "t" to "x" (You can similary use `[0-9]` to see if there's any number in a string). Use either of these methods to look for your favorite letters in `text`.

*** =instructions
- Search for the letters from "t" to "x".

*** =hint
- Use `re.search` and put `|` in the argument.

*** =pre_exercise_code
```{python}
text = "It was the best of times, it was the worst of times, it was the age of wisdom, it was the age of foolishness, it was the epoch of belief, it was the epoch of incredulity..."

```

*** =sample_code
```{python}
# Import re
import re

# Search for letters from t to x: results


# Print out the results
print(____)

```

*** =solution
```{python}
# Import re
import re

# Search for letters from t to x: results
re.search([t-x], text)

# Print out the results
print(results)

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

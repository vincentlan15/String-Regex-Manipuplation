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
## Searching for any character

Suppose you want to know if a string has any character at all, as opposed to an empty string or a string with only line break characters. What you need is to saerch with a ".". In regular expressions, "." belongs to the so-called "metacharacters" that signify certain structures in the pattern. Now, use it as the search pattern to find if there's any character in the string you are assigned, named `text`.

*** =instructions
- Import the `re` package.
- Use `re.search()` to check if there is any character in the object `text`.
- Print out the `results`.
- Click `Submit Answer` to print out the original `text` to see for yourself if there's any content in it.  

*** =hint
- The command to import package `x` is `import x`.
- Simply use "." as the search pattern.
- You don't need to change the code we provided for the first `print` statement.
- You don't need to change the code for the second `print` statement.

*** =pre_exercise_code
```{python}
text = "Keep up the good work!"

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
results = re.search("[t-x]", text)

# Print out the results
print(results)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:MultipleChoiceExercise lang:python xp:100 skills:1 key:06f58e3279
## What does this mean?

Find a string that will match with the following regular expression when using `re.search()`.
`"[cd]|\\ab"

*** =instructions
- a
- b
- \a
- \ab


*** =hint
- Recall what `\s`, and `+` mean.

*** =pre_exercise_code
```{python}

```

*** =sct
```{python}
msg1 = """Remember`\\` signifies a `\` in the string."""

msg2 = """Remember`\\` signifies a `\` in the string."""

msg3 = """The string has to containt either pattern in its complete form"""

msg4 = """Exactly!"""


test_mc(4, [msg1, msg2, msg3, msg4])
```

--- type:VideoExercise lang:python xp:50 skills:2 key:d46e7bc1da
## Pattern Repetition
- * repetition of previous pattern
- + one or more pattern
- ? 0 or not the preceeding pattern


--- type:NormalExercise lang:python xp:100 skills:1 key:536588d87c
## Find gene sequence pattern

In the gene sequence we have worked with, search for "C+" and "C*". Think before you submit the answer which pattern(s) will match. 

*** =instructions
- Search for "C+" in `seq`.
- Search for "C*" in `seq`.
- Print out both results

*** =hint
- Use `re.search()` to search for "C+" as the pattern.
- Use `re.search()` to search for "C*" as the pattern.
- You don't need to change the code for the print statement that we provided.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Import re
import re

# Assign the gene sequence to seq
seq = "ATGCTTCGGCAAGACTCAAAAAATA"

# Search for C+: results1


# Search for C*: results2


# Print out both results
print(____,____)

```

*** =solution
```{python}
# Import re
import re

# Assign the gene sequence to seq
seq = "ATGCTTCGGCAAGACTCAAAAAATA"

# Search for C+: results1
results1 = re.search("C+",seq)

# Search for C*: results2
results2 = re.search("C*",seq)

# Print out both results
print(results1,results2)
```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:5723a6e978
## Find repeated sequence

What if you are not only looking for repeated letters, but repeated sequence? For instance instead of looking for "C", "CC", "CCC"... you want to look for "CG", "CGCG", "CGCGCG"... You can group several letters together in `()`, and then search them as a unit. When you use `*` or `+`, Python searches for repetitions of the whole unit. Now, use this method to search for repetitions of "AT" using both `+` and `*`.   

*** =instructions
- Search for "AT" in `seq` using `+`.
- Search for "AT" in `seq` using `*`.
- Print out both results

*** =hint
- Use `re.search()` to search for "(AT)+" as the pattern.
- Use `re.search()` to search for "(AT)*" as the pattern.
- You don't need to change the code for the print statement that we provided.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Import re
import re

# Assign the gene sequence to seq
seq = "ATGCTTCGGCAAGACTCAAAAAATAT"

# Search for AT using +: results1


# Search for AT using *: results2


# Print out both results
print(____,____)

```

*** =solution
```{python}
# Import re
import re

# Assign the gene sequence to seq
seq = "ATGCTTCGGCAAGACTCAAAAAATAT"

# Search for AT using +: results1
results1 = re.search("(AT)+",seq)

# Search for AT using *: results2
results2 = re.search("(AT)*",seq)

# Print out both results
print(results1,results2)
```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:dd4e809615
## Matching an optional letter

Now it gets a bit more tricky: you are looking for a "T" and a "C" that are either consecutive or separated by a "G". How can you do that? A method we learned before, of course, is "TC|TGC", but now with the new `?` operator, we have a simpler way to express "the 'G' between the two other letters is optional." How exactly should the expression be? We leave the challenge to you.   

*** =instructions
- Search in `seq` for *all* occurences of "T" and "C" either consecutive or sepearted by a "G".
- Print out the results

*** =hint
- The search pattern should be `TG?C`.
- You don't need to change the code for the print statement that we provided.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Import re
import re

# Assign the gene sequence to seq
seq = "ATGCTTCGGCAAGACTCAAAAAATA"

# Search for ALL OCCURENCES of the pattern using ?: results


# Print out the results
print(____)

```

*** =solution
```{python}
# Import re
import re

# Assign the gene sequence to seq
seq = "ATGCTTCGGCAAGACTCAAAAAATA"

# Search for ALL OCCURENCES of the pattern using ?: results
results = re.findall("TG?C",seq)

# Print out the results
print(results)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:e3ef684864
## Using "." and "*" together

We learned earlier that "." can be used to match any character. Now that we have learned "*", we can use the two together to create powerful search patterns. A pattern such as "A.*G", for instance, means "an A followed by anything, and then G." Now use this technique to find *all occurences* of a C appearing before a G in the gene sequence we've been working on.   

*** =instructions
- Search in `seq` for *all* occurences of a "C" appearing before a "G".
- Print out the results

*** =hint
- The search pattern should be `C.+G`.
- You don't need to change the code for the print statement that we provided.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Import re
import re

# Assign the gene sequence to seq
seq = "ATGCTTCGGCAAGACTCAAAAAATA"

# Search for ALL OCCURENCES of the pattern: results


# Print out the results
print(____)

```

*** =solution
```{python}
# Import re
import re

# Assign the gene sequence to seq
seq = "ATGCTTCGGCAAGACTCAAAAAATA"

# Search for ALL OCCURENCES of the pattern: results
results = re.findall("C.+G",seq)

# Print out the results
print(results)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

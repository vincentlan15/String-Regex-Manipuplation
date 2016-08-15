---
title       : Text Mining
description : Now we've come to the fun part. With the techniques we've learned, we will create and use a text mining system which tries to predict the follow up word for a word. We will do this by analysing text. and building a data structure to hold the counts of follow up words. Let's get started!


attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:VideoExercise lang:python xp:50 skills:2 key:ef6777fad5
## What is text mining?
Explain the concept of this chapter. Tell them what we are going to do. We believe that in order to make a system that can predict which word comes next, we can use existing english texts, analyse their structure and use it to make predictions. Begin by explaining how to extract all words from a text. Use the split() function is a possibility. This gives problems with punctuation. Other option: re.findall().

--- type:NormalExercise lang:python xp:50 skills:1 key:8c8181cc6b
##Split up the words

Let's try extracting individual words with `split()`. If you use the function without any argument, it automatically splits words separated by a space, which is what we need. Now use `split` to extract the words from our familiar opening of "A Tale of Two Cities."

*** =instructions
- Use `split()` to extract individual words from `text` and save them to a list named `words`.
- Print out `words` to see the results.

*** =hint
- The basic syntax of `split` is `str.split()`.
- You don't need to change the code for the  print statement that we provided.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# assign the opening to the object text
text = "It was the best of times, it was the worst of times, it was the age of wisdom, it was the age of foolishness, it was the epoch of belief, it was the epoch of incredulity..."

# Aplit the words: words


# Print out the results
print(____)
```


*** =solution
```{python}
# assign the opening to the object text
text = "It was the best of times, it was the worst of times, it was the age of wisdom, it was the age of foolishness, it was the epoch of belief, it was the epoch of incredulity..."

# Split the words: words
words = text.split()

# Print out the results
print(words)
```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki


success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:50 skills:1 key:514818b19a
##Spliting words with findall()

As we noticed, `split()` doesn't work well with punctuations. Now we are going to use `re.findall()` to split words, which can ignore punctuations. Specifically, `\w+` matches any one or more characters, and finding all `\w+` effectively means finding all the words in a string. Now, use this technique to extract all the words in the text we worked with earlier.

*** =instructions
- Import the `re` package.
- Use `re.findall()` to find all the words in the object `text`.
- Print out the resuulting list.

*** =hint
- The command to import package `x` is `import x`.
- Pass `\w+` as an argument to `re.findall()`.
- You don't need to change the code we provided for the `print` statement.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Import re

# assign the opening to the object text
text = "It was the best of times, it was the worst of times, it was the age of wisdom, it was the age of foolishness, it was the epoch of belief, it was the epoch of incredulity..."

# Find all the words in text: results


# Print out the results
print(____)
```
*** =solution
```{python}
# Import re
import re

# assign the opening to the object text
text = "It was the best of times, it was the worst of times, it was the age of wisdom, it was the age of foolishness, it was the epoch of belief, it was the epoch of incredulity..."

# Find all the words in text: results
results = re.findall("\w+", text)

# Print out the results
print(results)
```
*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki

success_msg("Great work!")
```

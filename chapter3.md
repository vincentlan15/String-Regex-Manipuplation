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

--- type:NormalExercise lang:python xp:50 skills:1 key:37797e2e7b
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

--- type:MultipleChoiceExercise lang:python xp:100 skills:1 key:3e74f114a8
## How to lowercase

Which list comprehension would you use to normalise all words to their lower case form?

*** =instructions


*** =hint

*** =pre_exercise_code
```{python}
```

*** =sct
```{python}
msg1 = """`\s+` means space. It is not related to the letter `s`."""

msg2 = """Pay attention to `\"`, `\(` and other expressions for punctuations."""

msg3 = """Pay attention to all the `\s+` that signifies a space."""

msg4 = """Exactly!"""


test_mc(4, [msg1, msg2, msg3, msg4])
```
--- type:VideoExercise lang:python xp:50 skills:2 key:37e4e8e29d
## What data structure?
Given a list of words, which is in the correct order, you want to decide for each word, by which word it is followed each time. A nice resulting data structure would be a dictionary, where the keys are each unique word and the values are lists of follow up words. An even better data structure would be the same kind of dictionary, but with dictionaries as values. These dictionaries contain the frequency of follow up words. In the exercises we will gradually work to creating this data structure.

--- type:NormalExercise lang:python xp:50 skills:1 key:90c76c9afa
##Finding the next word

Let's use a for loop to find the follow up word for every word in the opening of `A Tale of Two Cities`. The words from the text are already split out and put into a list of the correct order named `results`.

*** =instructions
- Loop over the index of the object `results` except the last one.
- For every index, print out the word at the index and at the next index.

*** =hint
- Use a for loop over `range(len(results)-1)`.
- Use `test[i]` to find the word at the index `i`.

*** =pre_exercise_code
```{python}
results =   ['It', 'was', 'the', 'best', 'of', 'times', 'it', 'was', 'the', 'worst', 'of', 'times', 'it', 'was', 'the', 'age', 'of', 'wisdom', 'it', 'was', 'the', 'age', 'of', 'foolishness', 'it', 'was', 'the', 'epoch', 'of', 'belief', 'it', 'was', 'the', 'epoch', 'of', 'incredulity']
```

*** =sample_code
```{python}
# Loop over the results
for ____ in ____:
    print("the word " + ____ + " is followed by " + ____)

```

*** =solution
```{python}
# Loop over the results
for i in range(len(results)-1):
    print("the word " + results[i] + " is followed by " + results[i+1])

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:50 skills:1 key:435c74468f
##Creating a dictionary

Now that we know how to find the following word of each word in the text, we are going to create a dictionary to store all the information, where each key is a word in the text, and its value is a list of its following words. Use the same for loop as you used last time, but now add the following words to the dictionary


*** =instructions
- Create an empty dictionary named `dict`.
- Loop over the index of the object `results` except the last one.
- For each word, check if it is already a key in the dictionary by `if... in dict.keys()`.
- If not, create a list and put the following word into it. If so, append the following word to the list.

*** =hint
- Use `{}` to create an empty dictionary.
- Use a for loop over `range(len(results)-1)`.
- Check if `results[i]` is in `dict.keys()`.
- Call `dict[results[i]]` to initiate and update the list of the following words for `results[i]`.

*** =pre_exercise_code
```{python}
results =   ['It', 'was', 'the', 'best', 'of', 'times', 'it', 'was', 'the', 'worst', 'of', 'times', 'it', 'was', 'the', 'age', 'of', 'wisdom', 'it', 'was', 'the', 'age', 'of', 'foolishness', 'it', 'was', 'the', 'epoch', 'of', 'belief', 'it', 'was', 'the', 'epoch', 'of', 'incredulity']
```

*** =sample_code
```{python}
# Create an empty dictionary: dict


# Loop over the results
for ____ in ____:
    # Check if the word exists in the dictionary:
    if ____:
        # Update the list of following words:
        ____
    else:
        # Initiate the list of following words:        
        ____

print(dict)

```

*** =solution
```{python}
# Create an empty dictionary: dict
dict = {}

# Loop over the results
for i in range(len(results)-1):
    # Check if the word exists in the dictionary:
    if results[i] in dict:
        # Update the list of following words:
        dict[results[i]].append(results[i+1])
    else:
        # Initiate the list of following words:        
        dict[results[i]] = [results[i+1]]

print(dict)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:50 skills:1 key:435c74468f
##List comprehension
I actually don't know how to do listcomprehension.


*** =instructions
- Create an empty dictionary named `dict`.
- Loop over the index of the object `results` except the last one.
- For each word, check if it is already a key in the dictionary by `if... in dict.keys()`.
- If not, create a list and put the following word into it. If so, append the following word to the list.

*** =hint
- Use `{}` to create an empty dictionary.
- Use a for loop over `range(len(results)-1)`.
- Check if `results[i]` is in `dict.keys()`.
- Call `dict[results[i]]` to initiate and update the list of the following words for `results[i]`.

*** =pre_exercise_code
```{python}
results =   ['It', 'was', 'the', 'best', 'of', 'times', 'it', 'was', 'the', 'worst', 'of', 'times', 'it', 'was', 'the', 'age', 'of', 'wisdom', 'it', 'was', 'the', 'age', 'of', 'foolishness', 'it', 'was', 'the', 'epoch', 'of', 'belief', 'it', 'was', 'the', 'epoch', 'of', 'incredulity']
```

*** =sample_code
```{python}
# Create an empty dictionary: dict


# Loop over the results
for ____ in ____:
    # Check if the word exists in the dictionary:
    if ____:
        # Update the list of following words:
        ____
    else:
        # Initiate the list of following words:        
        ____

print(dict)

```

*** =solution
```{python}
# Create an empty dictionary: dict
dict = {}

# Loop over the results
for i in range(len(results)-1):
    # Check if the word exists in the dictionary:
    if results[i] in dict:
        # Update the list of following words:
        dict[results[i]].append(results[i+1])
    else:
        # Initiate the list of following words:        
        dict[results[i]] = [results[i+1]]

print(dict)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki

success_msg("Great work!")
```
--- type:MultipleChoiceExercise lang:python xp:100 skills:1 key:3e74f114a8
## How to lowercase

Which list comprehension would you use to normalise all words to their lower case form?

*** =instructions


*** =hint

*** =pre_exercise_code
```{python}
```

*** =sct
```{python}
msg1 = """`\s+` means space. It is not related to the letter `s`."""

msg2 = """Pay attention to `\"`, `\(` and other expressions for punctuations."""

msg3 = """Pay attention to all the `\s+` that signifies a space."""

msg4 = """Exactly!"""


test_mc(4, [msg1, msg2, msg3, msg4])
```

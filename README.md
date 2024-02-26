# 04-Wordle

---
title: "Wordle 04"
author: "Jessica V"
date: "`r Sys.Date()`"
output: html_document
---

```{r}
library(tidyverse)

#solution
google <- "https://raw.githubusercontent.com/difiore/ada-2024-datasets/main/google-10000-english-usa-no-swears.txt"

#official
scrab <- "https://raw.githubusercontent.com/difiore/ada-2024-datasets/main/collins-scrabble-words-2019.txt"

g <- read.table(google, header = TRUE, sep = "\t", stringsAsFactors = FALSE, fill = TRUE)
s<- read.table(scrab, header = TRUE, sep = "\t", stringsAsFactors = FALSE, fill = TRUE)

load_dictionary <- function(filename){
  read.delim(filename)
}

solution_list <- load_dictionary(google)
valid_list <- load_dictionary(scrab)

str(solution_list)
str(valid_list)

solution_list <-intersect(solution_list, valid_list)
```


#STEP 2: How many words are in your updates solution_list vector? 8336

#STEP 3:


```{r}
#library(stringr)

pick_solution <-



# strsplit()
##Write a custom function called pick_solution() that [1] removes all words from solution_list that are not 5 letters in length, 

#For [1], you will want to subset the solution_list vector according to some criterion of word length.
```



```{r}
library(stringr)
remain <- paste(str_extract_all(solution_list, '\\w{5,}'), collapse="")

```
#Here I am removing words 6 characters and longer but don't know how to romove the empty spaces that come up in quotations

```{r}
gsub("\\b[[:alpha:]]{6,}\\b", "", remain, perl=T)



```

#Attempt at only keeping words that are max 5 characters
```{r}
library(textTools)
str_rm_long_words(
  x = solution_list, 
  max_char_length = 5
  )
```


##Part2 of step 3:randomly choosing a single word from those that remain,
```{r}
sample(x, size, replace = FALSE, prob = NULL)

sample.int(n, size = n, replace = FALSE, prob = NULL,
           useHash = (n > 1e+07 && !replace && is.null(prob) && size <= n/2))




```











###### FAILED attemps bewlow, only keeping for personal learning reference
```{r}
library(qdapTools)

rm_nchar_words(solution_list, "1, 4")

rm_nchar_words(solution_list, "6, 10")

rm_nchar_words(solution_list, "5")

```

```{r}


unlist(strsplit(x, split=" "))
paste(z[nchar(z)>=3], collapse=" ")

```


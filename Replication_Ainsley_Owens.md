---
title: "Starter Notebook"
author: Ainsley Owens
format: html
execute:
  keep-md: true
---





### Intro to R Notebook

In this notebook, I will be exploring several functions of R and learning tools to complete the Replication Origin Notebooks. This will include using the arrow operator `<-`to store objects in variables, using R's `sample()` function to create random genomes for testing functions, and building functions to process and analyze genetic data. I will also be learning about for loops and reading in data from outside sources. These tools will be used to analyze genomes in future work.

### Challenge 1

Here I am using the `c()` function to put four nucleotides (A, G, C, T) into a list.


::: {.cell}

```{.r .cell-code}
Nucleotides <-c ("A","G","C","T")
Nucleotides
```

::: {.cell-output .cell-output-stdout}
```
[1] "A" "G" "C" "T"
```
:::
:::


### Challenge 2

Now, I will create a random string of 15 nucleotides, titled randGenome, using the `sample()` tool. Using the `<-` will store the list as randGenome.


::: {.cell}

```{.r .cell-code}
genome <- 15
randGenome <- sample(Nucleotides, size= genome, replace= TRUE)
randGenome
```

::: {.cell-output .cell-output-stdout}
```
 [1] "G" "C" "G" "A" "T" "A" "T" "T" "C" "A" "G" "G" "A" "A" "T"
```
:::
:::


Now, I will `collapse()` the genome to create a single string and make it easier to read.


::: {.cell}

```{.r .cell-code}
paste (randGenome, collapse="")
```

::: {.cell-output .cell-output-stdout}
```
[1] "GCGATATTCAGGAAT"
```
:::
:::


### Challenge 3

Now, I will create a random genome that is 1500 nucleotides long, using the `sample()` function again, naming this genome randGenome. I used the `paste()` function to collapse the list into a single string.


::: {.cell}

```{.r .cell-code}
genome <- 1500
randGenome <- sample(Nucleotides, size= genome, replace= TRUE)
paste (randGenome, collapse="")
```

::: {.cell-output .cell-output-stdout}
```
[1] "AACCATGCTGGGAGCGTACGCTACCCCATTTCCGAGTAGTTTCGGGCAAGACCCAACTGATACGTAGGAGCCTTTCAACGTAACCCATTTTGTAAGTTACTGTCTGCGCGGTTGAGATCCCTGACTCGATCACATACCGGCCGATGCACTTCAGGTAATGCCTGCATTTTACCCCATTACGACTAGTTGGGTTCCTGGAAAACCTTAAAGAGGGTCTTAATTTAAGCCTGTTGCGTTTCACAAGCTCCATTTGTCGTTCTTAGCGTTCAACGGGTCTCCTTGTTTGTTGGATAAACTCTCGGCAATAATGCAAGTCAGGATCCGCGTACAAACCCGCACCCGTTCCAAGGCGCCCGGCCAAAACCAATAAGAACTTGGATCGACCAGTACAGAAGTAGGCCATGGTCTCTAAGGCAAGCGTCTTATCGTCTGACTGTTTAACCACTGGGAAACCATTACGTAGATCTTTGCACTAGAGTACTAGCCAATGCCTAAACCCAATGTGGCAGCGCGCCAGACGACCGCAGGCAAGTTACCCCGCGTAGGTGTATGAGTCCCAGGGACTTGTTCTTACATGCTCCCGCATTAGCAGCCGTACAAAGATTGGACTCCTGTGGTCACTACTACCCGACGCGGTATCAATCAGCTCGCATGTCCCGTTACATCGATCACTACTCCTACTGATTCGCATTGACCCCTCCCGCCAAAGGACTGCCATTAGATTAGGCACAATTGGCACACGTTCCATAACATTGTCTGCTCATAGTCCATCCCAACCAAGTTACCCACAAGGAATAGACACGGATTGTAGGGCTCCCGCTGCAACGGTCTCATCGCCTACGTCGATATAATTTATGAAAACCGACAACGAGTGTTGCTTATTGATGATGGTGTTGAGACCTCGGGGCATGCCTATGCCGGGAGGCCGGCTGGACATTCTAGTGTGACTTTAAGCTTGTGCTAGTATCTGCCCGACAGTTAACGGAGGGGCCGAACCTGCAAGTATTGATTAATGGTTGCTAGAACTGCACACAGGAGATGAGTCATTAGACATTTCCAACGTGATTGGCAAAGGGCGAATACTAACCAGATCGTGCACGAAACAACGGGGTTGTTAGTAACAATGTTTGAACCATAATTGCAAGGTAGTTTTTAACCTGAGCGCACTAGCTACTACTATCCACACCTGCGCATGGATTGGGTTTCGTACAGTTCGTAAGTGGGCATTGCCGCCTAGCCCCGCTCTAGTAATTCTCGACTTAAATAGCAACCAGGCGGGATCTACGCGCCCGATAAAACGCTAAAGCATCGCTGGGTCGCAACCTTTATCTCTTACCACGCCGGAAGATGCGCCGAAGGAGGACCAACACGCCCTCCTGACGATACTATAACGCCGGACTCTTGTAGGGGATCTAGCAGATTACTCAGAGAGGAAAGGGAGCGCACAAACGCAACTACCTGATGACGCAAGGTCCTACGACTAGTTCTTGGGACCGGTGT"
```
:::
:::


Here, I am using `set.seed(215)` to initialize the random number generation with the seed 215, using the `paste()` function to collapse the list into one string. The `set.seed(215)` function guarantees that the same random values will be produced each time the code is ran, useful for reproducible results.


::: {.cell}

```{.r .cell-code}
set.seed(215)
genomeLength <- 1500

randGenome <- sample(Nucleotides, size = genomeLength, replace = TRUE)

randGenome <- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "TCCAATGTTTAATCTTGGCAGGTTTCACGGTGAACTTCCAGTAGGCGCCGGGGGCAGGCACACGTAAGTGTAAATCATCGAACGACGCGCTCGGCACTGTGTCTCCAGACCATGAGATTCCATCTCACGGAACATGTGCACATCAAAAAGAACTACCTTGTGTATGCGTCCGTGGAATGATTTTTATGGTTTCGTCGATAGTTATCCGGGTGGAAGGTTCGCAATTCGCCGATTAGCTTGTATCGAGCAAACACCGAGCACATCTATATGAGTGTTGACGTATGTCAGAGACCTACCGATTCCATCTGACGCTAGCAGGCCCCTACCGAAGGGGTTGTCTTCGGGGCGTCCGGCCATCGGAACCTCTTTTAGATGCCTATTTTAAACATCTCAAGTTAACTAAGGTAGTTACGTCAGCCCAACCTCGAGATCTATCTCTCAGTGTAGAGGAACATCGAGTTACCGATGAATAAAACTTCGGCCTTTCTAATGGTTCAGACTAATGCACATAATTAGTTCGCCCGAGATAAGGTAGTGCCTTGCTGGGGGTTACGCTAGCCCCCCCTCCCCAAGGATGACGCTTGCTATCTTACTGGTGGCCGATTTTTCCTGAGCCGGGTGGATCAAATAGATAGTACGCTCGGATTGGCCTGAAATCCGGGTCGCAACCATCGCCTCGCCTAACGCTCTCCCGGATAGTTCCCGACATTCACTTATAACAAAGACCGAAATTCCCAAGTACTCGCCGAGATCTAGACGTGCGAGTTGGTCCCCCCGCAGTAGGCAATTGGTACTATCTGTCACTACGCTAGGCCCGGACGTTTCCCTGGTGTTAGGTTCTAATCCCATGCCGGTTATCCCATCGGATCAGCAGAGTCGCCCACCTTAATAACTCTGGCGCATAAACGGTGCTCCTGCAAATGTCTTAGCTCGTGTTGTCTGATTTCGGATATTCCTAAACTTGAACACGGAGGGTATGTATTCAGTGGTACATGTGGGAAATCTATGGTGGAAGACTAGTTGAGGTCCATCCTAAGGGGAGGTGAATGAGGAGTTACCTGTGGACTAGTTTTCACGGCGGTAGCGCGTGTGCAAATAACGTAACGTACGTAGCCTGGCTCTTACCGCAAAAATCAATGGGTTTGGACGCGTAGGAACTCTACTGCCATCGCCTTCAGTTATCGGTCGGGCCTCACGACAATTTAAATGCGTCTAGGAATGACGAGTAGGAGAACCGCAAGCCCCGACGGAGCAGTCCGCGGAGAACGATCCAACCACTCTGCCCGCAAATGACCCGGCGATTAACGGCTTTTATGAGCCCTAAACACCTGAGATCTCGAGACACGGACATACTGCCGACTCAACCCGAGAAGCGTTTTTGCCGACCAACAGGGTTCGAGGTTTATGAGAGGCGCCCTGATGAGGCCGGAAACGACTGCCGCCTGAAGCTTAAAATTATTCGATCTGTACCTAAACGACCAGGACACACAGCTGCAAATG"
```
:::
:::


### Challenge 4

Using `set.seed(215)`, to ensure the same random sample is created each time I run the code, I created a random genome composed of 100 nucleotides, done by setting the `genomeLength` to `<-100`. The `paste()` function collapsed the list into one single strand.


::: {.cell}

```{.r .cell-code}
set.seed(215)
genomeLength <- 100
randGenome <- sample(Nucleotides, size = genomeLength, replace = TRUE)

randGenome <- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "TCCAATGTTTAATCTTGGCAGGTTTCACGGTGAACTTCCAGTAGGCGCCGGGGGCAGGCACACGTAAGTGTAAATCATCGAACGACGCGCTCGGCACTGT"
```
:::
:::


### Challenge 5

Here, I am learning how to create a for loop so I can create for loops to analyze genomes. A for loop is a control-flow construct used to run through a dataset and apply the same set of operations on each item in the dataset. To create a for loop, you must set an iterator and provide the instructions to be run each time through the loop. This simple for loop will multiply `myProduct`. I first initialized the container, `myProduct`, with a starting value of 1. By setting the `for(j in )` value to `1:15`, this instructs the loop to run through the range of integer values from 1 through 15. I then provided the condition on the iterator within a set of parentheses, ending the line with an open bracket. I will indent the next line, as the indented lines following the open bracket are where the instructions to be run through the loop are located.


::: {.cell}

```{.r .cell-code}
myProduct <- 1

for(j in 1:15){
  myProduct <- myProduct*j
  print(myProduct)
}
```

::: {.cell-output .cell-output-stdout}
```
[1] 1
[1] 2
[1] 6
[1] 24
[1] 120
[1] 720
[1] 5040
[1] 40320
[1] 362880
[1] 3628800
[1] 39916800
[1] 479001600
[1] 6227020800
[1] 87178291200
[1] 1.307674e+12
```
:::
:::


### Challenge 6

Here, I created a random genome consisting of 10 nucleotides. I then created a for loop intended to print each individual nucleotide as opposed to the whole string. I used `1:nchar()` to run the for loop through all characters in the string. I used the `str_sub()` function to extract individual nucleotides. The string subset function takes three arguments: the `string` to be subset, the position to `start` subsetting, and the position to `end` subsetting the string. If `start` and `end` are the same, a single character will be extracted. By using `str_sub()` and using `j` as both the `start` and `end` for subsetting, I was able to have the for loop print the individual nucleotides.


::: {.cell}

```{.r .cell-code}
set.seed(215)
genomeLength <- 10
randGenome <- sample(Nucleotides, size = genomeLength, replace = TRUE)

randGenome <- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "TCCAATGTTT"
```
:::

```{.r .cell-code}
for(j in 1:nchar(randGenome)){
  print (str_sub(randGenome,start= j, end=j))
         }
```

::: {.cell-output .cell-output-stdout}
```
[1] "T"
[1] "C"
[1] "C"
[1] "A"
[1] "A"
[1] "T"
[1] "G"
[1] "T"
[1] "T"
[1] "T"
```
:::
:::


### Challenge 7

Flow control is a programming concept used to execute code only when certain conditions are satisfied. This can be achieved using `if`, `else if`, and `else` statements. The code in Challenge 6 was adapted to only print occurrences of Adenine (`"A"`). This is done by using an `if` statement. I first initialized the container, `adenineCount`, with a starting value of 0. The `for` line instructs the code to run through all of the characters in the random genome. The `if` line instructs the code to only run if the current nucleotide in the random genome is Adenine (`"A"`). Because I already initialized the container with a starting value of 0, I can instruct the code to increment the value of the container by one every time an Adenine occurs, by following the `for` line, with `adenineCount <- adenineCount +1`. After closing the brackets for the flow control, I used the `print()` function to return the occurrences of Adenine.


::: {.cell}

```{.r .cell-code}
adenineCount <- 0
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "A"){
    adenineCount <- adenineCount +1
  }
}
 print(adenineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 2
```
:::
:::


### Challenge 8

Now that I have created a for loop to count the number of occurrences of Adenine in the string, I will adapt the loop to count the frequencies of each of the four nucleotides. I did so by setting containers for each nucleotide, `thymineCount`, `cytosineCount`, `adenineCount`, and `guanineCount`, to a starting value of zero. I then repeated the code used in Challenge 7, and changed the nucleotide in the `if` line to count each nucleotide, as well as the `nucleotideCount` line to the matching nucleotide to increment by 1 each time the nucleotide occurs. After closing the brackets for my loops, I printed each nucleotide count, using the `print(c(nucleotideCount))` function.


::: {.cell}

```{.r .cell-code}
thymineCount <- 0
cytosineCount <- 0
adenineCount <- 0
guanineCount <- 0
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "T"){
   thymineCount <- thymineCount +1
  
  }
   if(str_sub(randGenome, start = i, end = i) == "A"){
   adenineCount <- adenineCount +1
   }
   
  if(str_sub(randGenome, start = i, end = i) == "C"){
   cytosineCount <- cytosineCount +1
  
  }
  if(str_sub(randGenome, start = i, end = i) == "G"){
   guanineCount <- guanineCount +1
  
  }
}
print(c(thymineCount, adenineCount, cytosineCount, guanineCount))
```

::: {.cell-output .cell-output-stdout}
```
[1] 5 2 2 1
```
:::
:::


Here, I read in the Vibrio Cholerae genome, composed of 1,108,250 nucleotides, to test my code on a real genome. I named the dataset `vib_c`, and scanned the data in using the file path in my computer in quotations, followed by `, what = "character", sep = NULL`. These lines following the `scan` function must be in parentheses.


::: {.cell}

```{.r .cell-code}
vib_c <- scan("C:/Users/owens/OneDrive/Desktop/VibrioCholerae.txt", what = "character", sep = NULL)
```
:::


### Challenge 9

Now I can use the for loop I created to count all of the occurrences of the individual nucleotides in the cholera genome, by replacing `randGenome` with `vib_c`, to pull the nucleotides from the cholera genome.


::: {.cell}

```{.r .cell-code}
adenineCount <- 0
cytosineCount <- 0
guanineCount <- 0
thymineCount <- 0
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "T"){
   thymineCount <- thymineCount +1
  
  }
   if(str_sub(vib_c, start = i, end = i) == "A"){
   adenineCount <- adenineCount +1
   }
   
  if(str_sub(vib_c, start = i, end = i) == "C"){
   cytosineCount <- cytosineCount +1
  
  }
  if(str_sub(vib_c, start = i, end = i) == "G"){
   guanineCount <- guanineCount +1
  
  }
}
print(c(thymineCount, adenineCount, cytosineCount, guanineCount))
```

::: {.cell-output .cell-output-stdout}
```
[1] 294711 293942 263573 256024
```
:::
:::


### Challenge 10

Here, I used the `scan()` function to read in a Rosalind genome. I used the for loop previously created in Challenge 9 to count the occurrences of each nucleotide in the genome.


::: {.cell}

```{.r .cell-code}
rosalindSequence <- scan("C:/Users/owens/Downloads/rosalind_dna (6).txt", what = "character", sep = NULL)
```
:::

::: {.cell}

```{.r .cell-code}
rosalindSequence <- "AGAATGGACTTCTGTTAAAAAGTACGATACAATTAACACGCAGCGAATCCAGGTCGGGGCGTCTATCGACAGAAAAAGTGATCTAATGACTAGATGTGCGGTTAGGGTCATTAGTTGTACTAACCGCGGGTGCCGCGACCAACTAGATACGTATAACTAGACACGTTACCCGCTGCAATCGAACTCGCAAACCGAGCAACGCCCGTGGGCCATTATTACTATTAACAGGGAGGGATCGGTTTGAGCTCCCTTGTCTCGTAAAAATTTGGTTACGCTCAGTTGCATGCAATTCAGCGTGTGGTCGCTCTCGCTTGGCCCCCTCCAAGTGAACATCGAATAACGGTGGCCCGTAGCCAATTGCGGCAGTCGGGCCCGATAATCGACCGTGCGAGACATTCACTCGAATTTAATAGTTGTGCACTGTACCAGGGTATTCCATAGTTCACAAGCCGTTTACCAGGGCCTAAGCGCCAGAAGAGCTCGCACCTCTGAGACCTCAAACCCGCCCAGCAGGCGTATCCTGACATAGTAAGATCGGAGCCGGGTTTGGCGCGGTACACTACTACTCGTCGTCAAGTCATTTAAAGACGGAAGTAACTGCCTATAAGGTATCCCCCGGATCCGGACCGGTACCCTAAATCTGGTTCGTTAACAACCCGTCGGCCCGGGCCTCCAACAGACTTATTTGATTAGGGTGTATAAATGATTTGGCCCCAAGATATGTCGGCGTGCACCGTCTCTTATTCGTCCCCCGATAGGCGCGCTAGCAACATACAAATTCCTCTGGAGTGATGAGCCACGTCACACTGTTACGACATTTATCCGACCCACAGAAATGCGCGCAAGATCCGTACGCACGCGTACAGATGTCCACCTTTTTTGCCATAGGAAAGTGACCGAGTGCTCCGAGCGATACCAATCCGCCGGTAGTCCAGCTAGACTGTCTTA"
thymineCount <- 0
adenineCount <- 0
cytosineCount <- 0
guanineCount <- 0
for(i in 0:nchar(rosalindSequence)){
  if(str_sub(rosalindSequence, start = i, end = i) == "T"){
   thymineCount <- thymineCount +1
  
  }
   if(str_sub(rosalindSequence, start = i, end = i) == "A"){
   adenineCount <- adenineCount +1
   }
   
  if(str_sub(rosalindSequence, start = i, end = i) == "C"){
   cytosineCount <- cytosineCount +1
  
  }
  if(str_sub(rosalindSequence, start = i, end = i) == "G"){
   guanineCount <- guanineCount +1
  
  }
}
print(c(adenineCount,cytosineCount, guanineCount, thymineCount))
```

::: {.cell-output .cell-output-stdout}
```
[1] 243 256 230 219
```
:::
:::


Throughout this notebook, I learned several skills. I was able to create a list of nucleotides using `c()`. Using the `sample()` function, I was able to use the nucleotide list I provided to create a random genome. The `collapse()` function allowed me to collapse the genome into one single strand, as opposed to separate single characters. I learned that the `set.seed()` function allows for the code to set a seed for random number generation to enable reproducible results over time. I learned how to create a for loop to repeat instructions provided, and I used `if/else` statements to ensure the code is only ran when certain criteria is met. This notebook also taught me how to scan in data from other sources, like the vibrio genome and the Rosalind sequence, using the `scan()` function.

### Replication Origin I

In this notebook, I will be working towards developing code that can be used to find the origin of replication in a genome. Locating specific patterns in the genome are the first step in the process of determining the replication origin.

### Challenge 1

In the first code block, I am reading in the `nucleotide_frequency` function for further use. This function counts the number of occurrences of specific nucleotides, dependent on the nucleotide dictated in the first line of code. Using the `sample()` function alongside the `paste()` and `collapse""`, I generated a random genome with a length of 2000 nucleotides. Using the `nucleotide_frequency()` function, I was able to count the frequency of Cytosine, `"C"`, in the random genome.


::: {.cell}

```{.r .cell-code}
nucleotide_frequency <- function(genomeString, nucleotide = "A"){
  count <- 0
  for(i in 1:nchar(genomeString)){
    if(str_sub(genomeString, start = i, end = i) == nucleotide){
      count <- count + 1
    }
  }
  return(count)
}
```
:::

::: {.cell}

```{.r .cell-code}
  genome <- 2000
randGenome <- sample(Nucleotides, size= genome, replace= TRUE)
randGenome <- paste (randGenome, collapse="")
nucleotide_frequency(randGenome,nucleotide="C")
```

::: {.cell-output .cell-output-stdout}
```
[1] 499
```
:::
:::


### Challenge 2

In this challenge, I created a function to compute random genomes. This will make future work in this notebook easier because I no longer need to create genome lists, but instead can pull using the `rand_genome()` function. I provided the function with the nucleotide list to use, denoted the size parameter as k, and used the `paste()` and `collapse''` functions to create one string. To do so, I just need to insert `rand_genome()` and place the desired genome length in the parentheses, using the `k` parameter.


::: {.cell}

```{.r .cell-code}
rand_genome <- function(k){
  nucleotides <-c ("A", "T", "C", "G")
  rand_genome <- sample(nucleotides, size= k, replace= TRUE)
  rand_genome <- paste(rand_genome, collapse= "")
  return(rand_genome)
}
rand_genome(k=15)
```

::: {.cell-output .cell-output-stdout}
```
[1] "CTCCCCTATCCTAGC"
```
:::
:::


### Challenge 3

For this challenge, I will create a for loop that can run all the characters in a genome and count consecutive characters. This for loop will count and return all the substrings of 3 nucleotides in the genome, known as 3-mers. I used the `rand_genome()` function within the new `generate_3_mers` function that I created to generate a 2000 nucleotide sequence. The `generate_3_mers` function then reported all of the 3-mers in the genome.


::: {.cell}

```{.r .cell-code}
generate_3_mers <- function(genomeString) {
  list_3_mers <- c()

  for(i in 1:(nchar(genomeString) - 1)){
  list_3_mers <- list_3_mers %>%
  append(str_sub(genomeString, start = i, end = i + 2))
    }
  return(list_3_mers)
}

list_3_mers <- generate_3_mers(rand_genome(k=2000))
```
:::


To check if the function collected only 3-mers, I used the `tail()` function to print the last 25 substrings collected, using `n=`. I was able to call the `list_3_mers` data because I named the list in the previous code block. The tail function showed that the last substring was a 2-mer, not a 3-mer ("CA").


::: {.cell}

```{.r .cell-code}
tail(list_3_mers, n= 25)
```

::: {.cell-output .cell-output-stdout}
```
 [1] "CCT" "CTT" "TTT" "TTT" "TTA" "TAG" "AGA" "GAT" "ATT" "TTT" "TTG" "TGG"
[13] "GGG" "GGA" "GAG" "AGA" "GAG" "AGT" "GTT" "TTA" "TAA" "AAA" "AAA" "AAA"
[25] "AA" 
```
:::
:::


### Challenge 4

For this challenge, I am adapting the function from the previous challenge to create a function that reports k-mers of any size. I did so by adding the k value. I named the list `list_k_mers` so I am able to call upon this list during future work. The value next to rand_genome at the bottom of the code block determines how many characters the genome will be comprised of, while the value next to myGenome in the last line of code determines how long the k-mers reported by the function are. If I give the rand_genome function a value of 10, named myGenome, then the genome will be 10 nucleotides long. If I give the generate_k\_mers function a value of 5, pulling from myGenome, then the function will report the k-mers that are 5 nucleotides long.


::: {.cell}

```{.r .cell-code}
generate_k_mers <- function(genomeString, k) {
  list_k_mers <- c()

  for(i in 1:(nchar(genomeString) - (k-1))){
  list_k_mers <- list_k_mers %>%
  append(str_sub(genomeString, start = i, end = i + k-1))
    }
  return(list_k_mers)
}
myGenome <- rand_genome(10)
myGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "TTGATCTCTA"
```
:::

```{.r .cell-code}
generate_k_mers (myGenome, 5)
```

::: {.cell-output .cell-output-stdout}
```
[1] "TTGAT" "TGATC" "GATCT" "ATCTC" "TCTCT" "CTCTA"
```
:::
:::


### Challenge 5

Here, I created a function, `count_pattern`, to count occurrences of a particular pattern within a genome string. The bottom line of code, `count_pattern(myGenome, "")` tells R which pattern to count throughout the genome. This is function that will be adapted later in the challenge, so this code block is just the outline. In the `if` statement, the `end = i + 1)`, the +1 value can be adjusted to account for a larger pattern. The `count_pattern()` line can also be adjusted for future use. The `(myGenome, "TA")` can be adapted to a particular string and pattern, which will be seen next.


::: {.cell}

```{.r .cell-code}
count_pattern <- function(genomeString, pattern){
  count <- 0
  for (i in 1:nchar(genomeString)){
    if(str_sub(genomeString, start = i, end = i+1) == pattern){
      count = count + 1
    }
  }
  return(count)
}
  
count_pattern(myGenome, "TA")
```

::: {.cell-output .cell-output-stdout}
```
[1] 1
```
:::
:::


Here, I read in the Rosalind sequence to test that the code is properly working, naming it `rosalindString` using the `<-` arrow tool.


::: {.cell}

```{.r .cell-code}
rosalindString <- "CGCTGCAATGTGCAATGTTGCAATGTGCAATGAATTATGCAATGAATGCAATGTTGCAATGACTTGCAATGTATGCAATGGTGCAATGTTGCAATGTGCAATGTGCAATGACCATGCAATGTGCAATGTGCAATGAATTGCAATGTGCAATGTGCAATGTGCAATGTATGGCTGCAATGTGCAATGTGCAATGTGCAATGGTGCAATGCCAGTGCAATGGTTAAGTGCAATGAGTCTTGACTGCAATGTTTTGCAATGGTTTTGCAATGTGCAATGCTGCAATGGAATGCAATGTGCAATGCTGCAATGTGCAATGTGCGTAAGTGCAATGTGCAATGATGCAATGCCTGTCCATGCAATGTGCAATGTCGGTGCAATGTCATTATGCAATGTGAAGCGAATATGCAATGATGCAATGGTGCAATGTGCAATGTTGCAATGTGCAATGCAATGCAATGGTGCAATGATTTTGCAATGTTGCAATGCCTATACCTAGTCCATGCAATGTGCAATGGTAAATGCAATGGAGTGCAATGCTATGCCTTGCAATGTTGCAATGTGCAATGCTCCTGCAATGGCATGCAATGTGCAATGGTGCAATGGAACTGCAATGCTGCAATGATCCAGATCCGTGTGCAATGTTTGCAATGTGCAATGAGGGCGTTGCAATGCCGAGAGCTGCAATGGTGCAATGGTGCAATGACAGATGCAATGGTGCAATGGATGCAATGCCTGCAATGCTGCAATGTGCAATGTGCAATGATGCAATGTGCAATGTGCAATGGCCATTGCAATGTGCAATGTGCAATGTGATCAATTGCAATGTGCAATGTTGAATGCAATGCTATTCGGTCTGCAATGTTTGCAATGTGTGCAATGTGTGCAATGCTGCAATGTTTGCTGCAATGAAATATGCAATGCCCTTTGCAATGTGCAATGTTGCAATGATGCAATGGCCCGCTGCAATGAACATGTTGCAATGTGCAATG"
```
:::


In this code block, the outline function is adapted to run the Rosalind sequence. I adjusted the function by changing the if statement to `i+8`, because the pattern that is being looked for in the sequence is 9 characters long. In the last line of code, `count_pattern()`, I replaced the string to pull from rosalindString, and I copied in the pattern that is being counted, provided by Rosalind. Copying my solution into Rosalind, I determined that my answer is correct, meaning the code is working properly.


::: {.cell}

```{.r .cell-code}
count_pattern <- function(genomeString, pattern){
  count <- 0
  for (i in 1:nchar(genomeString)){
    if(str_sub(genomeString, start = i, end = i+8) == pattern){
      count = count + 1
    }
  }
  return(count)
}
  
count_pattern(rosalindString, "TGCAATGTG")
```

::: {.cell-output .cell-output-stdout}
```
[1] 37
```
:::
:::


While completing this notebook, I learned several skills and concepts. I learned to use functions to write reusable code, which can be helpful when trying to find similar things in several different genomes. Using functions to write reusable code prevents having to rewrite code several times to complete the same task within different genomes. I have worked more to learn how to understand and break down genomes using code. In this notebook, I learned how to count the number of occurrences of patterns in the genome.

### Replication Origin II

In this notebook, I will continue developing code with the goal of finding the replication origin in a genome. DNA replication begins in a certain position on the genome, known as the origin. This origin consists of a set of DNA sequences that signals the cells to start replication.

### Challenge 1

In bacteria, one of the proteins involved in replication is known as DnaA. DnaA binds to DnaA boxes, sequences in the genome, strings of 9 nucleotides that are more frequently repeated around the origin of replication.

In this challenge, I will write code to search for frequently occurring 9-mers. I will begin by using a previously created function to practice counting k-mers. Using the `generate_k_mers` function I previously created, I read in the sample sequence from the notebook guide and named it myGenome. By changing the value on the last line of code next to myGenome, I instructed R to report the 3-mers in the sequence.


::: {.cell}

```{.r .cell-code}
generate_k_mers <- function(genomeString, k) {
  list_k_mers <- c()

  for(i in 1:(nchar(genomeString) - (k-1))){
  list_k_mers <- list_k_mers %>%
  append(str_sub(genomeString, start = i, end = i + k-1))
    }
  return(list_k_mers)
}
myGenome <- "ACACAGACATCCCACCCC"
myGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "ACACAGACATCCCACCCC"
```
:::

```{.r .cell-code}
generate_k_mers (myGenome, 3)
```

::: {.cell-output .cell-output-stdout}
```
 [1] "ACA" "CAC" "ACA" "CAG" "AGA" "GAC" "ACA" "CAT" "ATC" "TCC" "CCC" "CCA"
[13] "CAC" "ACC" "CCC" "CCC"
```
:::
:::


I will now adapt the `generate_k_mers` function to create a function that will count and report frequently occurring k-mers. This code block is intended to find and count k-mers in the genome, loop through the list of k-mers and return the most frequently occurring k-mers. By giving `k` a value of 4, this code will return the most frequent 4-mer. I can change this `k` value to determine what length of most frequent k-mer is returned.


::: {.cell}

```{.r .cell-code}
frequent_kmers <- function(genome, k) {
  kmers <- generate_k_mers(genome, k)
  kmers <- unique(kmers)
  kmer_counts <- rep(0, length(kmers))
  for(i in 1: length(kmers)) {
    kmer_counts[i] <- count_pattern(genome, kmers[i])
  }
  max_count <-max (kmer_counts)
  frequent_kmers <- kmers[kmer_counts==max_count]
  return(frequent_kmers)
  
}

smallGenome <- "ATCCATTAT"
frequent_kmers(smallGenome, k=4)
```

::: {.cell-output .cell-output-stdout}
```
[1] "TTAT"
```
:::
:::


Now, to ensure my code is working properly, I will test it on a Rosalind sequence. This code block is using the Rosalind sample sequence before downloading the full genome.


::: {.cell}

```{.r .cell-code}
find_frequent_kmers <- function(genome, k) {
  kmers <- generate_k_mers(genome, k)
  kmers <- unique(kmers)
  kmer_count <- rep(0, length(kmers))
  for(i in 1: length(kmers)) {
    kmer_count[i] <- count_pattern(genome, kmers[i])
  }
  max_count <-max (kmer_count)
  frequent_kmers <- kmers[kmer_count==max_count]
  return(frequent_kmers)
  
}

rosalindGenome <- "ACGTTGCATGTCGCATGATGCATGAGAGCT"
find_frequent_kmers(rosalindGenome, k = 4)
```

::: {.cell-output .cell-output-stdout}
```
[1] "AGCT"
```
:::
:::

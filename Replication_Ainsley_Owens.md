---
title: "Starter Notebook"
author: Ainsley Owens
format: html
execute:
  keep-md: true
---





### Intro to R Notebook

In this notebook, I will be exploring several functions of R and learning tools to complete the Replication Origin Notebooks. This will include using the arrow operator `<-`to store objects in variables, using R's `sample()` function to create random genomes for testing functions, and building functions to process and analyze genetic data. I will also be learning about for loops and reading in data from outside sources. These tools will be used to analyze genomes.

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

Now, I will create a random string of 15 nucleotides, titled randGenome.


::: {.cell}

```{.r .cell-code}
genome <- 15
randGenome <- sample(Nucleotides, size= genome, replace= TRUE)
randGenome
```

::: {.cell-output .cell-output-stdout}
```
 [1] "T" "C" "G" "A" "G" "C" "G" "T" "G" "G" "C" "T" "T" "C" "C"
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
[1] "TCGAGCGTGGCTTCC"
```
:::
:::


### Challenge 3

Now, I will create a random genome that is 1500 nucleotides long. I used the `paste()` function to collapse the list into a single string.


::: {.cell}

```{.r .cell-code}
genome <- 1500
randGenome <- sample(Nucleotides, size= genome, replace= TRUE)
paste (randGenome, collapse="")
```

::: {.cell-output .cell-output-stdout}
```
[1] "TATTGCGGTATTAGCGTCGTCCTACGGGAACATTGTCCAGGGTACCTATAAAAATAAAGTAACCTTTAGAAACGTACATATGCTAATCTTCACGTTTCAGTCAACGCACCCGCGGATCACATCGAGAGTCGTACGGTCGTTAAAGATCTTCTAATTACCGATTCCAATGAAGAGCTTCATAGGAGTTGCACTATAAAATGATTGGCTGCATTGCACTGAGTCAACCACCGCTACTCATTCTACGGCTAACGCTTGATTATGTACCGCCACATGATGTGGACAAGAATGGGTCTGCCGTCGGGGTCGTTCATTTACCAGTGCGGTGCTTTTCACTGCCGACGGTGGTGTATGGGATTGTACAGGGACACGGGGATTTGAAATCAGAAAATGGATTGCTGGCTGATCAGTAGGTGATCTTTATCTTTACGAGCACTCCCTGAAGGCGGAGCATATATCGACGAAAATGCCACGGACGTCAGTTGTCCGCAGCCTTACGAATTTCTACGTCGGAAAAGATTGACCCAAGGCGGTTGCATGGCGTTGGGAACATTCCCGACCTGACGGTACAGCGTGATCGATTGATGATGCGAGGAGCCTTCCCCTAGATGCGAGGAAAATTATAACAGTTTGGGCGCCCGCGTGGCGGTCACCTCTCGTACATGAAACCACTGTGCAATCATTGAAACGGTCTCTGCGGAAATTAATTTCCCTGTATACGGTAGACATCCGATAGTGGTCTTACGGGACCATAACTTCGCTCGGGCGTAAAACCGGGTACTGAAACTGCCTTCCCCCATACCTCCGCGAGCGTTACAATACCTCCTGTGGTTTTTTACGATGTCTCTTGGCTAGGTTTTGCTATCGCGAAGGAAAGTGCTCGAATTTTGACATGGGTATATCATTTCCTGCCCCCAACAGGCACGAGTGTTACACATATCTGCCTTCGCACACATAATCAGCCTGTATATTGCGAGGTACTCCCCAACTAGCACTAGCCGGACGGCCGACACCCCTCCACCCAATTGGTTCAAAGGAATCGACTTAACTACCCAAGCGTGGCGTTTGATAAGTGGGGCGGAAACTGCGACGGGCAAGACGCCTAGTATAGTGAACGTATCGTATGTGCTTTTAAAACCCGAGTATAATCCCACATCCGGCTTGGAGATATCATAGGAACAGGATATTCGTACCCTCGGCGGACGTTAACGTGCACAAGGCAAACTTATTGTTCAACTGCTGACCAAAGTCTGAGTAAACAGCCAGTGGAACTAACTAAAAGTCTGAGTTGGTACGCGACATTTAGGCGTATTACACTTTTATCGGCATCTCTCATCAGAATCTGAAGTTCAGCGATGCTTGACTCGACATTCATGGTGTACATACCAGAATATCTTTCCGCGTAAGCAATACCATGAGGGGCAGATAATCTGCAGACTAAACCTGAATCAGTCTTGGAAAGGTCATTATTACAGACGCACGTTGTACTACACGGATTTACTG"
```
:::
:::


Here, I am using `set.seed(215)` to initialize the random number generation with the seed 215, using the `paste()` function to collapse the list into one string.


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

Using `set.seed(215)`, I created a random genome composed of 100 nucleotides. The `paste()` function collapsed the list into one single strand.


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

Here, I am learning how to create a for loop so I can create for loops to analyze genomes.


::: {.cell}

```{.r .cell-code}
myProduct <- 0

for(j in 1:15){
  myProduct <- myProduct + j
  print(myProduct)
}
```

::: {.cell-output .cell-output-stdout}
```
[1] 1
[1] 3
[1] 6
[1] 10
[1] 15
[1] 21
[1] 28
[1] 36
[1] 45
[1] 55
[1] 66
[1] 78
[1] 91
[1] 105
[1] 120
```
:::
:::


### Challenge 6

Here, I created a random genome consisting of 10 nucleotides. I then created a for loop intended to print each individual nucleotide as opposed to the whole string. I used `1:nchar()` to run the for loop through all characters in the string. I used the `str_sub()` function to extract individual nucleotides. By using `str_sub()` and using `j` as both the start and end for subsetting, I was able to have the for loop print the individual nucleotides.


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

Here, I adapted the for loop used in Challenge 6 to count the number of occurrences of Adenine in the string. I did this by creating the adenineCount variable, set to 0. I then removed the `print()` function previously used and replaced it with adenineCount, increasing the value by 1 every time there is an Adenine in the string, `adenineCount <-adenineCount +1`, then reinserted the `print()` function to print the count of Adenine occurrences.


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

Now that I have created a for loop to count the number of occurrences of Adenine in the string, I will adapt the loop to count the frequencies of each of the four nucleotides.


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
print(thymineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 5
```
:::

```{.r .cell-code}
print(adenineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 2
```
:::

```{.r .cell-code}
print(guanineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 1
```
:::

```{.r .cell-code}
print(cytosineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 2
```
:::
:::


Here, I read in the Vibrio Cholerae genome, composed of 1,108,250 nucleotides.


::: {.cell}

```{.r .cell-code}
vib_c <- scan("C:/Users/owens/OneDrive/Desktop/VibrioCholerae.txt", what = "character", sep = NULL)
```
:::


### Challenge 9

Now I can use the for loop I created to count all of the occurrences of the individual nucleotides in the cholera genome.


::: {.cell}

```{.r .cell-code}
thymineCount <- 0
cytosineCount <- 0
adenineCount <- 0
guanineCount <- 0
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
print(thymineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 294711
```
:::

```{.r .cell-code}
print(adenineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 293942
```
:::

```{.r .cell-code}
print(guanineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 256024
```
:::

```{.r .cell-code}
print(cytosineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 263573
```
:::
:::


### Challenge 10

Here, I used the `scan()` function to read in a Rosalind genome. I used the for loop previously created in Challenge 9 to count the occurrences of each nucleotide in the genome.


::: {.cell}

```{.r .cell-code}
rosalindSequence <- scan("C:/Users/owens/Downloads/rosalind_dna.txt", what = "character", sep = NULL)
```
:::

::: {.cell}

```{.r .cell-code}
thymineCount <- 0
cytosineCount <- 0
adenineCount <- 0
guanineCount <- 0
for(i in 1:nchar(rosalindSequence)){
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
print(adenineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 250
```
:::

```{.r .cell-code}
print(cytosineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 203
```
:::

```{.r .cell-code}
print(guanineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 230
```
:::

```{.r .cell-code}
print(thymineCount)
```

::: {.cell-output .cell-output-stdout}
```
[1] 244
```
:::
:::


Throughout this notebook, I learned several skills. I was able to create a list of nucleotides using `c()`. Using the `sample()` function, I was able to use the nucleotide list I provided to create a random genome. The `collapse()` function allowed me to collapse the genome into one single strand, as opposed to separate single characters. I learned that the `set.seed()` function allows for the code to set a seed for random number generation to enable reproducible results over time. I learned how to create a for loop to repeat instructions provided, and I used `if/else` statements to ensure the code is only ran when certain criteria is met. This notebook also taught me how to scan in data from other sources, like the vibrio genome and the Rosalind sequence, using the `scan()` function.

### Replication Origin 1

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

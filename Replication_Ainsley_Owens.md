---
title: "Starter Notebook"
author: Ainsley Owens
format: html
execute:
  keep-md: true
---





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
 [1] "T" "A" "G" "G" "C" "G" "T" "G" "C" "G" "A" "T" "C" "A" "T"
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
[1] "TAGGCGTGCGATCAT"
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
[1] "GGTGTCAGTCGCCCTAATACACGAGAGGCGTGATCCTTAACGGTCTAATGCTACAGCTGATCTATATGAAACGGTACTTAACGGCTCCTACGGATTACTGCTTAAAACTTACGAGCCCAAATCAAGGTTTATAAAGACAAAATTACGTGAGACACCTGGCTTTAATTTACATTTACGAGAACTCGATCGCCTCGCGTCAAGACTGGTAGGTTGGAAGCTGCGGTTAGAATGGTTATCCAAATTATTTGTCTACTGGTCAGGGCTCGGCAGGAGGTGTCATTATGGCGAACCGCCCTATATGTTCTTTCGTCCCCAAAAGTTCGTATAATGCAGCACTGAACAAGGTACGGTGCATGCCGCGGGAGATTACATTCGGGGAGAGCATGCAGCCCACACGGTTAGATCTCAAAAGAGATCAGTGAGAAAACTATGGGAGAAGCTGTAGGCAGCGCTTACCACGCCCCGGTCCCTCTAGCTCGAACGCGGCGGCGCGAGTTACCACACACAGGATGTAGTCAAAACGGAAAGTCTAGGGTAATTTGCAGTGGGAACAAGGGTGCGGTTACCGCTCCTAAAGCCCGATGCACGTCGTGCTGGACTTACGGGTGCAGACACTGGCCAAATGTAATCAGAAGCACCGCGACCGAGTAGATTTGGGGAAAGACCAACTTGTACTTCATAGTTGCCGCATGGGCCCCAAACTCAACTTACGAACGAGTCACGAAGCCGAGTAATAGATACGTGCTGTAATCTAATCTACGGCTGGGGCGTTACTTAGCCTAAAATCTCAGGTTTAACCTCAAAGTGATTCATGCAAAATCATCATTGGTACCCGCGGCTGACTTGCCGTCAAGATTGGACAGTACACCCATATGCGTTTTCGGCATGCCAAGGATTTCTCGATGCCTATACGACGGAGCTCCAAAGTTTTACGTCTTCAAAACCATTATACAGCCTACTCTGATCAAATCAATCCACGGCACGGTAGGATGTGCTATTCCATACCACTCGGACCACTTACGAACGTTCCAGTCTCACCCGGCATAAGACATGCCCTGACGAATAGGAATTCACACTCGTCTGCGCTAAACCTTCTGTGACATTCCGGCGATCAAGTGTGCCGGATATGGAACAAAGCGCTCTTCTGTCCGAGTTTGTACGTCCTGGGAATCAGAATCCGCCTTTCGATCAAGTGGGGTGTGAATCGCCATGCTCCCGGAAGTTGCGCAAGAAGATCTGCCGCTGGGCTCTTGTGCGACGGACCAAGACTCCCAACTTCGTCCGTGTCCTGATACGACCTTTCCACGTCCGCCGACTTGCCTGAGAATGCATTCGAGCTGAGGAGAGTTCGTAGCAAGTGACAAGCGACCTGCTTCCTTGGCAAACACGGTTTAGCCTCTGATCAGTTGTGTGGATGTTGGGTCATCAAAGGACTCCCGAAAGGGGCTATCTCGGGCAAGAGAACTGCTTTGAAATTAATCGATCCCTCTCAACATTGTA"
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
    print(adenineCount)
  }
}
```

::: {.cell-output .cell-output-stdout}
```
[1] 1
[1] 2
```
:::
:::


### Challenge 8

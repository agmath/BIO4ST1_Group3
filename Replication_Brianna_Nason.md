---
title: "Group 3 Project"
author: "Brianna Nason"
format: html
execute:
  keep-md: true
---





## Getting Started

You've used Quarto Notebooks a few times already, so you're starting to get the hang of this. Start by editing the Notebook `title:` and make sure you credit yourself as the `author:`. As a reminder, R-code appears in grey chunks throughout your notebook. Anything within these grey blocks must be executable R code. When you are outside of an R chunk, in a section of the notebook with a white background, you can type freely as if you were in a typical Word document.

You'll quickly see the value of including text to explain your code chunks, and motivate your analysis. Trying to get help from a notebook that doesn't effectively use these discussions will be quite difficult. Additionally, future *you* will be very thankful to present-day *you* if you document your analyses well, and will be quick to curse present-day *you* when you do not.

Now, remove this *Getting Started* text and you'll be ready to start sciencing.

## Challenge 1


::: {.cell}

```{.r .cell-code}
Nucleotides <- c("A", "C", "G", "T")
Nucleotides
```

::: {.cell-output .cell-output-stdout}
```
[1] "A" "C" "G" "T"
```
:::
:::


## Challenge 2


::: {.cell}

```{.r .cell-code}
randGenome <- 15
schedule <- sample(Nucleotides, size = randGenome, replace = TRUE)
schedule
```

::: {.cell-output .cell-output-stdout}
```
 [1] "T" "T" "G" "A" "C" "A" "T" "A" "G" "C" "G" "G" "G" "G" "A"
```
:::

```{.r .cell-code}
paste(randGenome, collapse = "")
```

::: {.cell-output .cell-output-stdout}
```
[1] "15"
```
:::
:::


## Challenge 3


::: {.cell}

```{.r .cell-code}
Genome_size <- 1500
randGenome <- sample(Nucleotides, size = Genome_size, replace = TRUE)
randGenome<- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "ACGTTCCGGCACGATTATCCAGAGCCCTCACGCTGTTTCTCAGCGGTACATCTTATGGTAGCTTACTTTAGGGCACCGGTAAGCCTCGGTTGGAACTGGACATTGGGAAATTCATGGACATGAGGACTTTAGGTGCTCTTGTAGACAGACTGGTCAATGGCGGGTGCTCCGCAAGGGGGGATGGGCCCGGAAGCCAAACCCTCGTAGCCCTGATTCCGCCAAACGCGGTTATAGGGGTCCCAGGCATTCGGGGGCACGATGTATTCCGAGTCAGCGGACAGCGGCATTTAGCCTTGTCGTGAGTCGTACTTCCATCGGTTCCTCAAGAATTTATTATCGCCGCTCGCGGTGAAAGTTGAAGAAGCGAAGGTACAGTTCGGCCATTGATGTTTAGTGCAATGGTCAAAAATTGGCGTCTGGTTCGCGGTCGCATAAGAAGCCTATAACCAGATCCACTCCAGCTGCGTTTACGCAGACTAAACCCTTCGTGGAGCACCACTCAGAACGCATACACGTAGCCTTGGTTGGGATACAACTTCATGTCATGCGGCGGTTCCCAGCCGGATGAGGATAAGTTTAAGACCGCGGCCAAAGCCGCCGACTCCGAAGATCGTCTGAGAGCGAGGGGATGTAATAGAGCCCGATGCAAAGATAGATGTGTACTTTATAGTTTTTGCGGGAGGTTGCAAATATTCTAGACCAAATTGTAATTTTTCCGTCGTGGATGTTTAGACTCGCAATCGATATATTACTTAAGTGCCCATGCATTCTACTAGTGGCAGGAGCTCAGTAAATGTATACCCAGGGCTGCCGACAATTCGCGCAGGATGAAGGTGGTGCTACTAAGGTAAGTAGAGGACCGACTTGTATTATATTATAAGCTGGGGGACCGTTTCGACGTTGGGTACATCATTCACTTCGTAATTCGCTAGTGCCCTTAGTAAATATTATAAATTGTTAGCAAAGGCGAGGTAACGCAACTTAGACTATCACCATTCGATGCCAGCGTCAGGATAGATCAATACAGCAACTTCGCGACGCGGTGCCGATGTCCAGTTTCGGGACCTCTATACCGCGGACTACCCGGCGTAGCGCATAAGACTGCTGATGACTCGAATGCTAATAGCTTGCAACATTTCAAAGTGGATTACTTCTTGAATGAATGCCAGACGGCTACTCGCGTAACTACCGACAGGTGCTAACTGCTTGGACGGAATATCTCATTATGTAATCAGCAAAAACCTGTGCGTTCGCAAGCGCCTAACCCACTTGGTCTTATATGATCAAGAGTGAACGTGGGGTTAGTAGTACCGTCCGTCTACGACACCGTCGCGTTTAAAGTCTACTATAGGGAATTGGTAGCTGCGGGGCGCACCCAGTCCGCTAGCAATATAACCAGCCCGATTTTGTCCATCATCACGCGATTTAATGAAAATCTGCTTTTCCGTTGTTCGCGAGCGGCTATTTTCGAAGGCGGTCGTGGTCTACGTCCAGTCGGGG"
```
:::
:::

::: {.cell}

```{.r .cell-code}
set.seed(215)
Genome_size <- 1500
randGenome <- sample(Nucleotides, size = Genome_size, replace = TRUE)
randGenome <- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "TGGAATCTTTAATGTTCCGACCTTTGAGCCTCAAGTTGGACTACCGCGGCCCCCGACCGAGAGCTAACTCTAAATGATGCAAGCAGCGCGTGCCGAGTCTCTGTGGACAGGATCACATTGGATGTGAGCCAAGATCTCGAGATGAAAAACAAGTAGGTTCTCTATCGCTGGCTCCAATCATTTTTATCCTTTGCTGCATACTTATGGCCCTCCAACCTTGCGAATTGCGGCATTACGTTCTATGCACGAAAGAGGCACGAGATGTATATCACTCTTCAGCTATCTGACACAGGTAGGCATTGGATGTCAGCGTACGACCGGGGTAGGCAACCCCTTCTGTTGCCCCGCTGGCCGGATGCCAAGGTGTTTTACATCGGTATTTTAAAGATGTGAACTTAAGTAACCTACTTAGCTGACGGGAAGGTGCACATGTATGTGTGACTCTACACCAAGATGCACTTAGGCATCAATAAAAGTTGCCGGTTTGTAATCCTTGACAGTAATCGAGATAATTACTTGCGGGCACATAACCTACTCGGTTCGTCCCCCTTAGCGTACGGGGGGGTGGGGAACCATCAGCGTTCGTATGTTAGTCCTCCGGCATTTTTGGTCACGGCCCTCCATGAAATACATACTAGCGTGCCATTCCGGTCAAATGGCCCTGCGAAGGATGCGGTGCGGTAAGCGTGTGGGCCATACTTGGGCAGATTGAGTTATAAGAAACAGGCAAATTGGGAACTAGTGCGGCACATGTACAGCTCGCACTTCCTGGGGGGCGACTACCGAATTCCTAGTATGTCTGAGTAGCGTACCGGGCCAGCTTTGGGTCCTCTTACCTTGTAATGGGATCGGCCTTATGGGATGCCATGACGACACTGCGGGAGGTTAATAAGTGTCCGCGATAAAGCCTCGTGGTCGAAATCTGTTACGTGCTCTTCTGTCATTTGCCATATTGGTAAAGTTCAAGAGCCACCCTATCTATTGACTCCTAGATCTCCCAAATGTATCCTCCAACAGTACTTCACCTGGATGGTAACCCCACCTCAATCACCACTTAGGTCTCCAGTACTTTTGAGCCGCCTACGCGCTCTCGAAATAAGCTAAGCTAGCTACGGTCCGTGTTAGGCGAAAAATGAATCCCTTTCCAGCGCTACCAAGTGTAGTCGGATGCGGTTGACTTATGCCTGCCCGGTGAGCAGAATTTAAATCGCTGTACCAATCAGCACTACCACAAGGCGAACGGGGCAGCCACGACTGGCGCCACAAGCATGGAAGGAGTGTCGGGCGAAATCAGGGCCGCATTAAGCCGTTTTATCACGGGTAAAGAGGTCACATGTGCACAGAGCCAGATAGTCGGCAGTGAAGGGCACAACGCTTTTTCGGCAGGAAGACCCTTGCACCTTTATCACACCGCGGGTCATCACCGGCCAAAGCAGTCGGCGGTCAACGTTAAAATTATTGCATGTCTAGGTAAAGCAGGACCAGAGAGACGTCGAAATC"
```
:::
:::


## Challenge 4


::: {.cell}

```{.r .cell-code}
set.seed(215)
Genome_size <- 100
randGenome <- sample(Nucleotides, size = Genome_size, replace = TRUE)
randGenome <-paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "TGGAATCTTTAATGTTCCGACCTTTGAGCCTCAAGTTGGACTACCGCGGCCCCCGACCGAGAGCTAACTCTAAATGATGCAAGCAGCGCGTGCCGAGTCT"
```
:::
:::


## Loops


::: {.cell}

```{.r .cell-code}
mySum <- 0
for(i in 1:10){
  mySum <- mySum + i
  print(mySum)
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
```
:::
:::


## Challenge 5


::: {.cell}

```{.r .cell-code}
myProduct <- 1
for(j in 1:15){
  myProduct <- myProduct + j
  print(myProduct)
}
```

::: {.cell-output .cell-output-stdout}
```
[1] 2
[1] 4
[1] 7
[1] 11
[1] 16
[1] 22
[1] 29
[1] 37
[1] 46
[1] 56
[1] 67
[1] 79
[1] 92
[1] 106
[1] 121
```
:::
:::


## Challenge 6


::: {.cell}

```{.r .cell-code}
Genome_size <- 10
randGenome <- sample(Nucleotides, size = Genome_size, replace = TRUE)
randGenome<- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "CTGTGGACAG"
```
:::

```{.r .cell-code}
for(i in 1:nchar(randGenome)){
    print(str_sub(randGenome, start = i, end = i))
  }
```

::: {.cell-output .cell-output-stdout}
```
[1] "C"
[1] "T"
[1] "G"
[1] "T"
[1] "G"
[1] "G"
[1] "A"
[1] "C"
[1] "A"
[1] "G"
```
:::
:::


## Flow Control


::: {.cell}

```{.r .cell-code}
Nucleotides <- c("A", "C", "G", "T")
Genome_size <- 10

randGenome <- paste(
  sample(Nucleotides, size = Genome_size, replace = TRUE),
                   collapse = "")
print(randGenome)
```

::: {.cell-output .cell-output-stdout}
```
[1] "GATCACATTG"
```
:::

```{.r .cell-code}
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "A"){
    print(str_sub(randGenome, start = i, end = i))
  }
}
```

::: {.cell-output .cell-output-stdout}
```
[1] "A"
[1] "A"
[1] "A"
```
:::
:::


## Challenge 7


::: {.cell}

```{.r .cell-code}
Nucleotides <- c("A", "C", "G", "T")
Genome_size <- 10

randGenome <- paste(
  sample(Nucleotides, size = Genome_size, replace = TRUE),
                   collapse = "")
print(randGenome)
```

::: {.cell-output .cell-output-stdout}
```
[1] "GATGTGAGCC"
```
:::

```{.r .cell-code}
Adenine_count <- 0
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "A")
    Adenine_count <- Adenine_count + 1
    
    print(Adenine_count)
  }
```

::: {.cell-output .cell-output-stdout}
```
[1] 0
[1] 1
[1] 1
[1] 1
[1] 1
[1] 1
[1] 2
[1] 2
[1] 2
[1] 2
```
:::
:::


## Challenge 8


::: {.cell}

```{.r .cell-code}
Nucleotides <- c("A", "C", "G", "T")
Genome_size <- 10

randGenome <- paste(
  sample(Nucleotides, size = Genome_size, replace = TRUE),
                   collapse = "")
print(randGenome)
```

::: {.cell-output .cell-output-stdout}
```
[1] "AAGATCTCGA"
```
:::

```{.r .cell-code}
Adenine_count <- 0
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "A")
    Adenine_count <- Adenine_count + 1
    
    print(Adenine_count)
}
```

::: {.cell-output .cell-output-stdout}
```
[1] 1
[1] 2
[1] 2
[1] 3
[1] 3
[1] 3
[1] 3
[1] 3
[1] 3
[1] 4
```
:::

```{.r .cell-code}
Cytosine_count <- 0
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "C")
    Cytosine_count <- Cytosine_count + 1
    
    print(Cytosine_count)
}
```

::: {.cell-output .cell-output-stdout}
```
[1] 0
[1] 0
[1] 0
[1] 0
[1] 0
[1] 1
[1] 1
[1] 2
[1] 2
[1] 2
```
:::

```{.r .cell-code}
Guanine_count <- 0
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "G")
    Guanine_count <- Guanine_count + 1
    
    print(Guanine_count)
}
```

::: {.cell-output .cell-output-stdout}
```
[1] 0
[1] 0
[1] 1
[1] 1
[1] 1
[1] 1
[1] 1
[1] 1
[1] 2
[1] 2
```
:::

```{.r .cell-code}
Thymine_count <- 0
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "T")
    Thymine_count <- Thymine_count + 1
    
    print(Thymine_count)
  }
```

::: {.cell-output .cell-output-stdout}
```
[1] 0
[1] 0
[1] 0
[1] 0
[1] 1
[1] 1
[1] 2
[1] 2
[1] 2
[1] 2
```
:::
:::


## Challenge 9


::: {.cell}

```{.r .cell-code}
vib_c <- scan("/Users/briannanason/Documents/Bioinformatics info/VibrioCholerae.txt", what = "character", sep = NULL)
```
:::

::: {.cell}

```{.r .cell-code}
Adenine_count <- 0
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "A")
    Adenine_count <- Adenine_count + 1
}

Cytosine_count <- 0
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "C")
    Cytosine_count <- Cytosine_count + 1
}

Guanine_count <- 0
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "G")
    Guanine_count <- Guanine_count + 1
}

Thymine_count <- 0
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "T")
    Thymine_count <- Thymine_count + 1
}

print(c(Adenine_count, Cytosine_count, Guanine_count, Thymine_count))
```

::: {.cell-output .cell-output-stdout}
```
[1] 293942 263573 256024 294711
```
:::
:::


## Challenge 10


::: {.cell}

```{.r .cell-code}
vib_c <- scan("/Users/briannanason/Downloads/rosalind_dna.txt", what = "character", sep = NULL)
```
:::

::: {.cell}

```{.r .cell-code}
vib_c <- "TGAATCGCCATAGACCAGGTAGCACCACGGATCGACCGTGCAAGTCCCACATATACCATGTGTTAGTGAAATATTGCGCTTAGGTCCGCAGATAAGAGTGTTTGACAAGGCGGGTAAATACAATATCAGAATCAAGTCGGCTAAACGAGCTCATGATTGGACTGCTTGAACAGTTTAGCGAGTTGCGGGTGACTTACCTGTACGGTGCACGCGTTTTCGTGGAGAACTTTAAGCCCTCGCCAACGTGTTGTAATAGCCTCCTGCTCACCGGCCTCCTATATCCAGACATTGCGACTAGTGCGCATACACCTACTCTTATTTATAAGAACATAAATTGCGCTAACCGTAATGCCTAACACTATGTTCGTGGCTTCGGGTACCAAGGTACCGATGGCACGGGTCGCAACCCGATACGAGCTCTATTGTGGATACTAACTCTGTGATCGTCGCGACAAGATTTGCGAGATTGGGTGGCGTTGAGCAGCAGGCCCCGAACGGTAAACTTACTTGCACGCGATTGGACAAGGAAGTAAATACGCGACTTGAACCCTTATAGAACTTTTAGAGTCGGAATGAGTTATCGAGTCCCAATGGGCTTGTATCTGGGCTGGTTGTCACCTACGCTTCCGAAGACAACATCTAGATTGAGATCAGGTGGTGAGTCTTACACCAATGATTGATACGCTTCACTTGGCGGGCGAGTCCTTGGATAGCTCGCTGCGTTAGCGATTTTCACCCAGTCAGTATTGATTCATTAACTCGGGCGAACTAGATCACTCCCTGAGTAGGGCGCGGACACGCGGTATTGCTGCTAGGGGTGCGTGAACGGAACCACTG"

Adenine_count <- 0
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "A")
    Adenine_count <- Adenine_count + 1
}

Cytosine_count <- 0
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "C")
    Cytosine_count <- Cytosine_count + 1
}

Guanine_count <- 0
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "G")
    Guanine_count <- Guanine_count + 1
}

Thymine_count <- 0
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "T")
    Thymine_count <- Thymine_count + 1
}

print(c(Adenine_count, Cytosine_count, Guanine_count, Thymine_count))
```

::: {.cell-output .cell-output-stdout}
```
[1] 211 197 217 212
```
:::
:::


## Origin Replication I

## Challenge 1


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

nucleotide_frequency("ACTTGCGGGTATCGAG", "G")
```

::: {.cell-output .cell-output-stdout}
```
[1] 6
```
:::
:::

::: {.cell}

```{.r .cell-code}
Nucleotides
```

::: {.cell-output .cell-output-stdout}
```
[1] "A" "C" "G" "T"
```
:::

```{.r .cell-code}
Sample_genome <- sample(Nucleotides, size=2000, replace=TRUE)
Sample_genome <- paste(Sample_genome, collapse="")
nucleotide_frequency(Sample_genome, "C")
```

::: {.cell-output .cell-output-stdout}
```
[1] 485
```
:::
:::


## Challenge 2


::: {.cell}

```{.r .cell-code}
rand_genome <- function(k){
  Nucleotides <-c ("A", "T", "G", "C")
  rand_genome <- sample(Nucleotides, size=k, replace = TRUE)
  rand_genome <- paste(rand_genome, collapse="")
  return(rand_genome)
}
rand_genome(k=15)
```

::: {.cell-output .cell-output-stdout}
```
[1] "AATGAGGGGCGGAGG"
```
:::
:::


## Challenge 3


::: {.cell}

```{.r .cell-code}
generate_3_mers <- function(myString) {
  list_3_mers <- c()

  for(i in 1:(nchar(myString) - 2)){
  list_3_mers <- list_3_mers %>%
  append(str_sub(myString, start = i, end = i + 2))
    }
  return(list_3_mers)
}

myGenome <- rand_genome(10)
myGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "GCTTACGAAC"
```
:::

```{.r .cell-code}
generate_3_mers(myGenome)
```

::: {.cell-output .cell-output-stdout}
```
[1] "GCT" "CTT" "TTA" "TAC" "ACG" "CGA" "GAA" "AAC"
```
:::
:::


## Challenge 4


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
[1] "GTAGGGTCAG"
```
:::

```{.r .cell-code}
generate_k_mers(myGenome, 6)
```

::: {.cell-output .cell-output-stdout}
```
[1] "GTAGGG" "TAGGGT" "AGGGTC" "GGGTCA" "GGTCAG"
```
:::
:::


## Challenge 5


::: {.cell}

```{.r .cell-code}
count_pattern <- function(genomeString, pattern){
  count <- 0
  for(i in 1:nchar(genomeString)){
    if(str_sub(genomeString, start = i, end = i+1) == pattern){
      count = count + 1
    }
  }
  return(count)
}
  
count_pattern(myGenome, "AT")
```

::: {.cell-output .cell-output-stdout}
```
[1] 0
```
:::
:::


## Challenge 5

Rosalind Challenge


::: {.cell}

```{.r .cell-code}
rosalind_string <- "TGCTGAACTTTATGCTGAATGCTGAATGCTGAATGCTGAATTGCTGAACCTTGCTGAATGCTGAAATGCTGAAGTATGCTGAATGCTGAAGTGCTGCTGAATGCTGAATGCTGAATGCTGCTGAATGCTGAACATGCTGAACTGCTGAAGTGTCATGCTGAAGGCGATAGGCTGCTGAATTCTTTGCTGAAGTGCTGAATGCTGAAATGCTGAACCTGCTGAAAGTGCTGAATGCTGAATCTTATGCTGAAATGCTGAATGCTGAATGCTGAATGTGCTGAATTTGCTGAATGCTGAACATGCTGAATCCAGGTCTGCTGAAGGTGCTGAAGAGAATCACTGCTGAAAATTGCTGAAACTGTTAGCTGCTGAAATTTGCTGAATGCTGAATGCTGAATCGCCTGCTGAATTATGCTGAATGATGCTGAATCGTGCTGAAGTGCTGAATGCTGAAACATACTGCTGAACGTGCTGAATGCTGAACCCATGCTGAATTGCTGAAACCTGCTGAAACTGCTGAAAGTGCTGAATGCTGAATGCTGAAAGACTGCTGAATGCTGAAATGCTGAAGTGCTGAACACGTGCTGAATGCTGAACGTGCTGAATGCTGAAAATCTGCTGAATGCTGAAGTGCTGAATGCTGAATGCTGAATTGCTGAACAATTGCTGAATGCTGAACTAATGTTTCTGCTGAAGCTAACTGCTGAATGCTGAAGTCGAATCGAACTTGCTGAATCAGGTGCTGAATGATCTCATCTGCTGAACCCGTGCTGCTGAATGTGCTGAACGGATGCTGAAAATGTGCTGAACCGCCACTGCTGAAAAGTGCTGAAAACAGTGCTGAAGGCTGCTGAATTGCTGAATGCTGAATGCTGAAGTGCTGAAATGGGATATGCTTGCTGAAATGCTGAAGAGCATGCTGAATGCTGAATGCTGAAATTGCTGAAATATTCTACATACATACGTGCTGAATCTTGCTGAATGCTGAATCGGTGCTGAACTATGCTGAACTGCTGAATGCTGAATCAATTGCTGAA"
count_pattern <- function(myString, pattern){
  count <- 0
  for(i in 1:nchar(myString)){
    if(str_sub(myString, start = i, end = i+8) == pattern){
      count = count + 1
    }
  }
  return(count)
}
  
count_pattern(rosalind_string, "TGCTGAATG")
```

::: {.cell-output .cell-output-stdout}
```
[1] 38
```
:::
:::


## Origin Replication II

## Challenge 1


::: {.cell}

```{.r .cell-code}
find_frequent_kmers <- function(genome, k){
  #Get the Kmers
  kmers <- generate_k_mers(genome,k)
  kmers <- unique(kmers)
  #count occurrences
  kmer_counts <- rep(0,length(kmers))
  for(i in 1:length(kmers)){
    kmer_counts[i] <- count_pattern(genome, kmers [i])
  }
max_freq <- max(kmer_counts)
freq_kmers <- kmers [kmer_counts= max_freq]
return(freq_kmers)
}

find_frequent_kmers("ACACAGACATCCCACCCC",3)
```

::: {.cell-output .cell-output-stdout}
```
[1] "ACA"
```
:::
:::

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
generate_k_mers("ACACAGACATCCCACCCC",3)
```

::: {.cell-output .cell-output-stdout}
```
 [1] "ACA" "CAC" "ACA" "CAG" "AGA" "GAC" "ACA" "CAT" "ATC" "TCC" "CCC" "CCA"
[13] "CAC" "ACC" "CCC" "CCC"
```
:::
:::

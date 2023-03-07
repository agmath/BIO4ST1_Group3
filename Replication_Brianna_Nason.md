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
 [1] "A" "G" "T" "T" "A" "T" "T" "C" "C" "C" "A" "T" "G" "T" "C"
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
[1] "TAAATTACTTCATCGACTAAACAATTCGGCTTACGGAGCCCGCATAGTAAAACGCTCAAACCCGCCCAGAGCGGAGTTCGTGCTCCCTTATGGTTCTAAGATAATCGTGGACACTGCCTAATGGAAGCGCGGTCGTATAAGAGTTGACTACTTGCTTTCTCATTCACTTAGCGACCTCCTCACATCGACCATGTACTTGCTTCGCGGGAAAGCCTTAGTGTGTAATGACAGAAGCATTGAGGGCTGACTGATCACCCCGTGAACGGTTCCTCCACACGACGGGTGGTGACGGTCTCGGTCGAAAGCCTTTTGATCTTGTTGGCATGCTCTCGATATTGAGAGCACTCCCAGTGTGACGAGATGGACTATAACGGGACCAGACAGGTATCGTTCCTGTTGTGGGCGTACCGTATGGTAGGTTCACCCAGGTGGAACACATGTCACGTCCTTGCCTAAAATATAGGCTGACTTACGGCTGCACGGCCTAGACATGTTCCCATAAATCCGACGGCAGCAAGAAGAGTCAACTCTCCCAAACCGACCAATAACTCGGGTGTGCAGAATTCGACCTAGGAGCCTTCTGGGCCATCCAGGACCGTTGGTTATGGTAAGGTTATGTTGTGACGTGCCTGTCGAGGATATTACCTGGTATGTTCTGTTCGTAATAGTATACGGATGAAACGCTTTTCTCGGGTCGGCACATGGGATTGTGGTATCTGCCTCGTTATGCATTTCCAATGTCTGGCACATATGGGTGCTTATCCTGACCGAGCGGATAAGCGGCCTATAGCAAGGCGCCGTTTCGCTGATTAAGTGTGGCTGTGGGTCTAAAATATTATACACGGACTCCATCAAGTTGAAAGGATTAAATATCCCGGGTCTAGCCTCGTAGTGACACGCCGGAGTCGGCTCCTTGAGATCCGCACGTCTTCGCTCCCTTTTCGAAAATAAGATGTCATGACGATTAGACCCTTAAAACTTGCGTTCAACTCCGCATCTAATCTACATAATAGTTATGGCGTGTTGCCCCACCACGTCGGCCAATTCGACGCGGTATTGCTTATCCCTCACTTGCTGTCAGAACGGGGGCATAGCCCTCTTGATGACGGCTGATAAGAGGCTTAAGTGCATCCCGTTGCCGAGACTCAGGCCTTTGACTGGCCGCGGAATGAAAAGAATAATGACGCGGTCCATTAGATCCATTAGTTGATTCCGTAAAGTGTCCTCGGTGCCTGCTGTTGCTGACCCTACGATTCTGTAACCTCATTTGCAGCGGCCAACAAACAAGAGAACCCTAGCTTCAAAGCTCGCTAGAATTTTGGCCTCGCAATCCTCCAAGGGACTCCGTGCTCGACAGGGGCAGTATCACCGAGGTATAGGGCATCTAGCGTCTCAGTGTTGCCTGTAGCACAGTCGGATTCAGTTCCGCAATGAACGTTTATGTCATTAGGTATTATCGTCGGATACGTCCAGTACGCCGTAAATAAGGGGCGACCCGAT"
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

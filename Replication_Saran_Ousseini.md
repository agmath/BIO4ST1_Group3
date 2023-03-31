---
title: "Group 3 project"
author: "Saran Ousseini"
format: html
execute:
  keep-md: true
---





## Challenge 1


::: {.cell}

```{.r .cell-code}
nucleotide <- c("A", "C", "T", "G")

nucleotide
```

::: {.cell-output .cell-output-stdout}
```
[1] "A" "C" "T" "G"
```
:::
:::

::: {.cell}

```{.r .cell-code}
numNucleotide <- 15

randGenome <- sample(nucleotide, size = numNucleotide, replace = TRUE)

randGenome
```

::: {.cell-output .cell-output-stdout}
```
 [1] "C" "A" "A" "T" "C" "G" "T" "T" "T" "T" "A" "T" "G" "G" "T"
```
:::
:::


Challenge 2


::: {.cell}

```{.r .cell-code}
paste(randGenome, collapse = "")
```

::: {.cell-output .cell-output-stdout}
```
[1] "CAATCGTTTTATGGT"
```
:::
:::


## Challenge 3


::: {.cell}

```{.r .cell-code}
set.seed(200)
genomeLength <- 1500

randGenome <- sample(nucleotide, size = genomeLength, replace = TRUE)

randGenome <- paste(randGenome, collapse = "")
randGenome 
```

::: {.cell-output .cell-output-stdout}
```
[1] "CCTGTGGACGCCTGTGGAGCTGGTCACCTGCTTTAACTGTAGCACGCGCTGTTAGACCCTACTGCAAAACGTATGAGCTACTAGACGCTGCTTCCCTGCATGCATTTGATTTAGTATGACTAGGCCGCTCGACACCCACTCTGCAGTATCTTGAAATGGACTCCTTGTTTTGAAGGTCGCCATATTCTCTAGAAACTACATTCAGAATGAATTCGTGTCCCAGAATCAGTTCGCACCGACGCACGAGGTAGTTAGGTCTGCGCCTCATGACTTGGGGTCGCCTACTTTTAGCTCCTCGGACCGACCACCCGCAGCCCAGATCTATGGACTGCTACATCCTACCGCGTATATGCCCTGCTTGAGAATGCGTCGCATGTTCGATGGAAGTTTAGTCAGATCGCGACCAACTTCATAAATAATCTGATTGGGGATTAACAGTGATGAGGATTCAGTATGAAAGTCCTATGGAGAGTTTTTCGCATTGACAGACTAACAGCGCAGTAATGCTTGTTGACCTGTATAGAGCCGGACGCGCTGTCACAATCTCTCTTACCCGCGTTAGGTTCTGGCCTCACGCCCGTGCACTGAGGAGAATTTGGTCGGCCTTTGTACTAATATAGCCGACTCTAGACAAATGGCTAAGATCGTCTTCGTTGAGCGTATCAACCTTGGCCAGACGTGCTTACTATGTCAACCCAAATTAAACCCTCACTGCGAGTAATGAGGCGTTAGCGGCGGAAGATTGCTTGCGTTCCAGACGTATCGCATAGATCCGTGAACCGACCTCATCAAGCGTCTTGCTGGGCACTCGAGCAGCCTTACTGGGGCCCTTCTTTCGCAATCTACGCCTTAGGCCGCGTTAGACCAGCCGTCTAGCCTGTGGCTGGATACCCAATCTCGAGGCTCGCGAGATCAACCATCATCCGAGACAGACCGTGAAGCAACGCGGAACGTCGGGTCACGCTTAGGTAATATTGAAGTAGCGAATTGACGTTCGGCTTGCTGCGACGCGAGTACAGGCAGGCAACCTCATGGCAGAGGTAACGAATGTTCCGGAGCGTTTACGTTGCCATGGGAATGTTTCATCTTACGACAGTCAGCCGGTCATCGTAAATTCGTCATGTAAACGTCACGAATAGATGAATCGCGTCTTTCTGAAAATCGCGAACTCGTGTTCACACCCTGCAATGACATTGCCGGATTGAACCGCTCACCATACTCACGCTGAACACACTGCCCTGTACTAGATATCACAGAGTGTTTCGGGTCCAGAACGTACGCATCACATTCACTCGGGAGGCTGATTGGCGTCTGCCGAGCAGAACGAGATGGTTGGGAGACTATAGGCAGAGCACGATGGGAAGCCGCTAAGGCACTGTCATTGGAGCGCATGCGCTCCCCCTCCGTTCTCAAACCCAACGCTCTTCGATCTCAGCGCGTGTCATAGTAAGTGGCACGGCTCCTACGCAAAGTTATAACAGCGTAAGTTAGGTGGGACCA"
```
:::
:::


## Challenge 4


::: {.cell}

```{.r .cell-code}
set.seed(215)
genomeLength <- 100

randGenome <- sample(nucleotide, size = genomeLength, replace = TRUE)

randGenome <- paste(randGenome, collapse = "")
randGenome 
```

::: {.cell-output .cell-output-stdout}
```
[1] "GTTAAGCGGGAAGTGGCCTACCGGGTATCCGCAATGGTTACGACCTCTTCCCCCTACCTATATCGAACGCGAAAGTAGTCAATCATCTCTGTCCTATGCG"
```
:::
:::


I counted 23 Adenine (A)


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

for (j in 1:15) {
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
nucleotides <- c("A", "C", "G", "T")
genomeLength <- 10

randGenome <- paste(
  sample(nucleotides, size = genomeLength, replace = TRUE),
                   collapse = "")
print(randGenome)
```

::: {.cell-output .cell-output-stdout}
```
[1] "CTGTGGACAG"
```
:::
:::


## Challenge 7


::: {.cell}

```{.r .cell-code}
for(i in 0:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "A"){
    print(str_sub(randGenome, start = i, end = i))
  }
}
```

::: {.cell-output .cell-output-stdout}
```
[1] "A"
[1] "A"
```
:::
:::


## Challenge 8


::: {.cell}

```{.r .cell-code}
vib_c <- scan("/Users/saranousseini/Desktop/VibrioCholerae.txt", what = "character", sep = NULL)

#vib_c
```
:::


## Challenge 9


::: {.cell}

```{.r .cell-code}
CountA <- 0
CountT <- 0
CountC <- 0
CountG <- 0

for(i in 0:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "A"){
    CountA <- CountA + 1}
  
  if(str_sub(randGenome, start = i, end = i) == "T"){
    CountT <- CountT + 1}
  if(str_sub(randGenome, start = i, end = i) == "C"){
   CountC <- CountC + 1}
  if(str_sub(randGenome, start = i, end = i) == "G"){
    CountG <- CountG + 1}  
}
print(c(CountA, CountT, CountC, CountG))
```

::: {.cell-output .cell-output-stdout}
```
[1] 2 2 2 4
```
:::
:::


## Challenge 10


::: {.cell}

```{.r .cell-code}
CountA <- 0
CountT <- 0
CountC <- 0
CountG <- 0

for(i in 0:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "A"){
    CountA <- CountA + 1}
  
  if(str_sub(vib_c, start = i, end = i) == "T"){
    CountT <- CountT + 1}
  if(str_sub(vib_c, start = i, end = i) == "C"){
   CountC <- CountC + 1}
  if(str_sub(vib_c, start = i, end = i) == "G"){
    CountG <- CountG + 1}  
}
print(c(CountA, CountT, CountC, CountG))
```

::: {.cell-output .cell-output-stdout}
```
[1] 293942 294711 263573 256024
```
:::
:::


# Replication0rigin_PartI


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


## Challenge 1


::: {.cell}

```{.r .cell-code}
nucleotide <- c("A", "C", "T", "G")

nucleotide
```

::: {.cell-output .cell-output-stdout}
```
[1] "A" "C" "T" "G"
```
:::

```{.r .cell-code}
set.seed(200)
genomeLength <- 2000

randGenome <- sample(nucleotide, size = genomeLength, replace = TRUE)

randGenome <- paste(randGenome, collapse = "")
randGenome 
```

::: {.cell-output .cell-output-stdout}
```
[1] "CCTGTGGACGCCTGTGGAGCTGGTCACCTGCTTTAACTGTAGCACGCGCTGTTAGACCCTACTGCAAAACGTATGAGCTACTAGACGCTGCTTCCCTGCATGCATTTGATTTAGTATGACTAGGCCGCTCGACACCCACTCTGCAGTATCTTGAAATGGACTCCTTGTTTTGAAGGTCGCCATATTCTCTAGAAACTACATTCAGAATGAATTCGTGTCCCAGAATCAGTTCGCACCGACGCACGAGGTAGTTAGGTCTGCGCCTCATGACTTGGGGTCGCCTACTTTTAGCTCCTCGGACCGACCACCCGCAGCCCAGATCTATGGACTGCTACATCCTACCGCGTATATGCCCTGCTTGAGAATGCGTCGCATGTTCGATGGAAGTTTAGTCAGATCGCGACCAACTTCATAAATAATCTGATTGGGGATTAACAGTGATGAGGATTCAGTATGAAAGTCCTATGGAGAGTTTTTCGCATTGACAGACTAACAGCGCAGTAATGCTTGTTGACCTGTATAGAGCCGGACGCGCTGTCACAATCTCTCTTACCCGCGTTAGGTTCTGGCCTCACGCCCGTGCACTGAGGAGAATTTGGTCGGCCTTTGTACTAATATAGCCGACTCTAGACAAATGGCTAAGATCGTCTTCGTTGAGCGTATCAACCTTGGCCAGACGTGCTTACTATGTCAACCCAAATTAAACCCTCACTGCGAGTAATGAGGCGTTAGCGGCGGAAGATTGCTTGCGTTCCAGACGTATCGCATAGATCCGTGAACCGACCTCATCAAGCGTCTTGCTGGGCACTCGAGCAGCCTTACTGGGGCCCTTCTTTCGCAATCTACGCCTTAGGCCGCGTTAGACCAGCCGTCTAGCCTGTGGCTGGATACCCAATCTCGAGGCTCGCGAGATCAACCATCATCCGAGACAGACCGTGAAGCAACGCGGAACGTCGGGTCACGCTTAGGTAATATTGAAGTAGCGAATTGACGTTCGGCTTGCTGCGACGCGAGTACAGGCAGGCAACCTCATGGCAGAGGTAACGAATGTTCCGGAGCGTTTACGTTGCCATGGGAATGTTTCATCTTACGACAGTCAGCCGGTCATCGTAAATTCGTCATGTAAACGTCACGAATAGATGAATCGCGTCTTTCTGAAAATCGCGAACTCGTGTTCACACCCTGCAATGACATTGCCGGATTGAACCGCTCACCATACTCACGCTGAACACACTGCCCTGTACTAGATATCACAGAGTGTTTCGGGTCCAGAACGTACGCATCACATTCACTCGGGAGGCTGATTGGCGTCTGCCGAGCAGAACGAGATGGTTGGGAGACTATAGGCAGAGCACGATGGGAAGCCGCTAAGGCACTGTCATTGGAGCGCATGCGCTCCCCCTCCGTTCTCAAACCCAACGCTCTTCGATCTCAGCGCGTGTCATAGTAAGTGGCACGGCTCCTACGCAAAGTTATAACAGCGTAAGTTAGGTGGGACCATAAATGTCGGGTAGAATCGTCCGATATGAAAATGCTGGTGATCGCGAGATCCCGCATCCTCATGAGTAGTCTCCAACCTGTACTAGCGGACTATAGATCAGTCGGTCGCAAACGTGACCATCCACGCTCAAATCGCCTATTCTGTGTTTTAAGAGCTGAATCCCCGTGCATGTGTGGGATGACCATTGAGATTTCGCCCGTAAGCTTCCTTAGTGCAAATGGCAACAAAGAGCGAAACGTAGATTCGTAAGGGGCATTCGGCTGAATGTAATGCTAATGCTCCTACGCCGGCGGACGATTGTCATAGATTCCCGAGTAGTAAGAACATCCATGTTAACGATTGGTACAACTGCAAAAATTTCGATTCAAAGTATGTTGCGGGTCTTTGCCTTGCTTTATGAACGAAGGTCCGTGTTTTGCGCGACCAAACGTGTTTAACATTCGCAGAGCAGTGGGTGCATCAGTAAGGTAGCGTTACTGTTAATCTTCCACCGACCGTA"
```
:::

```{.r .cell-code}
nucleotide_frequency(randGenome, "C")
```

::: {.cell-output .cell-output-stdout}
```
[1] 509
```
:::
:::


## Challenge 2


::: {.cell}

```{.r .cell-code}
randGenome <- function(k){
  nucleotide <- c("A", "C", "T","G")
randGenome <- sample(nucleotide, size = k, replace = TRUE)

randGenome <- paste(randGenome, collapse = "")
randGenome 

  return(randGenome)
}

randGenome(5)
```

::: {.cell-output .cell-output-stdout}
```
[1] "ATTGC"
```
:::
:::

::: {.cell}

```{.r .cell-code}
myString <- randGenome

str_sub(randGenome(), start = 1, end = 2)
```

::: {.cell-output .cell-output-stdout}
```
[1] "TC"
```
:::
:::

::: {.cell}

```{.r .cell-code}
generate_2_mers <- function(myString) {
  list_2_mers <- c()

  for(i in 1:(nchar(myString) - 1)){
  list_2_mers <- list_2_mers %>%
  append(str_sub(myString, start = i, end = i + 1))
    }
  return(list_2_mers)
}

generate_2_mers(randGenome())
```

::: {.cell-output .cell-output-stdout}
```
[1] "GC" "CG" "GT"
```
:::
:::


## Challenge 3


::: {.cell}

:::

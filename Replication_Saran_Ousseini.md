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
 [1] "C" "A" "C" "T" "T" "C" "C" "C" "C" "G" "A" "T" "A" "T" "C"
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
[1] "CACTTCCCCGATATC"
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

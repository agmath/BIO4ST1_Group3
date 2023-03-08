---
title: "Starter Notebook"
author: "Skylar Pietz"
format: html
execute:
  keep-md: true
---





## Getting Started

You've used Quarto Notebooks a few times already, so you're starting to get the hang of this. Start by editing the Notebook `title:` and make sure you credit yourself as the `author:`. As a reminder, R-code appears in grey chunks throughout your notebook. Anything within these grey blocks must be executable R code. When you are outside of an R chunk, in a section of the notebook with a white background, you can type freely as if you were in a typical Word document.

You'll quickly see the value of including text to explain your code chunks, and motivate your analysis. Trying to get help from a notebook that doesn't effectively use these discussions will be quite difficult. Additionally, future *you* will be very thankful to present-day *you* if you document your analyses well, and will be quick to curse present-day *you* when you do not.

Now, remove this *Getting Started* text and you'll be ready to start sciencing.

# Challenge 1


::: {.cell}

```{.r .cell-code}
# Challenge 1

nucleotides <- c("A", "C", "G", "T")
nucleotides
```

::: {.cell-output .cell-output-stdout}
```
[1] "A" "C" "G" "T"
```
:::
:::


Challenge 1 involved creating a list of the four nucleotides- A, C, G, and T.

# Challenge 2


::: {.cell}

```{.r .cell-code}
# Challenge 2

Genome <- 15 
randGenome <- sample(nucleotides, size = Genome, replace = TRUE)
randGenome
```

::: {.cell-output .cell-output-stdout}
```
 [1] "G" "G" "A" "A" "A" "T" "A" "A" "G" "T" "G" "A" "C" "C" "T"
```
:::
:::

::: {.cell}

```{.r .cell-code}
randGenome <- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "GGAAATAAGTGACCT"
```
:::
:::


In challenge 2 I used code to create a random string of 15 nucleotides. Additional code (paste) was used to collapse the genome of nucleotides into a single string, so it's easier to read. When I compared my collapsed genome with a classmate, I noticed that we generated very different genomes.

# Challenge 3


::: {.cell}

```{.r .cell-code}
# Challenge 3

Genome <- 1500 
randGenome <- sample(nucleotides, size = Genome, replace = TRUE)
randGenome <- paste(randGenome, collapse = "" )
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "ACTTTTCTCGCGTAAACCGTTGGCCGCAATGTGAACTGTACTACATGCCTTCGAATTACGAATGCGCAGAGCAGCGGTTCCAAGCTGCAATCGGCCTACGCCGTAGGTCTTACCATATTGGGACTTTGTTTCAGAGAGACAGTCTTCTGAGGGAATACAAGGATAGGGCAGTATTACGTCGTGCGGCGTCCCTATAATACATCCATGATGATCGAGGGTTGTAATGACAAATACCACCCCCCATGTCACGAGCCGGATTATGCCCGGGAGTTAAGTTTCGACAATAGGGGCCAGTAGACCACTACCGGTCATAAGCCACAGAGGCAAGTATACGCAATCAATAGCAATTACTCCGTGAGTAGTTAAGAGATTCAACGCAAGTCGTGGGATGCTCTATACTAAAAGGTGTCGTCTTGAAAAGCTGGTAAATAAGGTTCCCGACGGAGGGGAGTGTATATATAAAGGGCAGTGCTATGGTAGCAATGCCCCTACCGATAAACTCAGACAGTGCAGGGACTATAAGTAGAGGTGTTCACTCCTGGCTCACAGGTACAGGGTCGAGTGCGGATCATTACTTGAGAGTCCGTACCCCGCTATGTGACTTACTGTACCACAGACCTGACATTGCCCTTAGGAAGGGAGCGTGGGCGTAACTAAGGAATGTATGTCCTACTTATCCATTATTACACGTCTGCTATATGGAGCCCAGCTAATCTCATATAAAGCAATTTTGACCTGCCTAGGGTAAACCGTGCAATCAGCTGTTGGATGCATCCGCCGAGGCGGTGCTCGCAGACATCAGACCAACGTATCATTCCTGCCAGTGGACGGCTTGCATATGTGTGGGACTATGGATCATTTCCTCTAGTCCTCTATAGCTACAGAGTCTCGTCCGTATATAACGTTCCGACGGAATTGTTGCACTGAGCCATTGTCGACTAACCTCAGCCTAGTGCCAAAAGCCGGCGGTCTACGAATTGACTGAATTAGACATTGGTGTCTGGGCAGGTAATATTAGAGCCCCATAGTCCCTACGAAGGCGTTCCTCTAATCGCGTTAGTCCAGGCATATCCAGCTCTTGTCGTTCCCGAACTTCTTCCATTCACGTACCTTTCGGCCTACCCCCGTAATATTAGCAACCTGCTTGGTAAACCATGGGCGTAGCTCCCCCGCTCATATCAAGCCCACGCTTAGTTAACTTGCAGAGTTTGTCAGTAGAGACGTCACCGCGGAACACGACACATTCTACTGCTTCAGAGACTCTCGTGGACGACAGATTGACAGCTCATTTGTATGGGTACCGTAAGGCGAAGTAAACGATTTGAGCTCCCCACAATGCGGCTGGTCACCACTCCCTACCACCAGATATGGTCCCGATATTGTCAATTCCTTCGCTAATGAACTGGATTGTGAAAGCCGGTGACAGTAGCGGAAACCTAATGATGGAATAGGGTACACGTGAGCCCGCCATTTGTGTGCTCCACTAAAGCGAATCATGGG"
```
:::
:::

::: {.cell}

```{.r .cell-code}
# Challenge 3 continued

set.seed(215)
genomeLength <- 1500

randGenome <- sample(nucleotides, size = genomeLength, replace = TRUE)

randGenome <- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "TGGAATCTTTAATGTTCCGACCTTTGAGCCTCAAGTTGGACTACCGCGGCCCCCGACCGAGAGCTAACTCTAAATGATGCAAGCAGCGCGTGCCGAGTCTCTGTGGACAGGATCACATTGGATGTGAGCCAAGATCTCGAGATGAAAAACAAGTAGGTTCTCTATCGCTGGCTCCAATCATTTTTATCCTTTGCTGCATACTTATGGCCCTCCAACCTTGCGAATTGCGGCATTACGTTCTATGCACGAAAGAGGCACGAGATGTATATCACTCTTCAGCTATCTGACACAGGTAGGCATTGGATGTCAGCGTACGACCGGGGTAGGCAACCCCTTCTGTTGCCCCGCTGGCCGGATGCCAAGGTGTTTTACATCGGTATTTTAAAGATGTGAACTTAAGTAACCTACTTAGCTGACGGGAAGGTGCACATGTATGTGTGACTCTACACCAAGATGCACTTAGGCATCAATAAAAGTTGCCGGTTTGTAATCCTTGACAGTAATCGAGATAATTACTTGCGGGCACATAACCTACTCGGTTCGTCCCCCTTAGCGTACGGGGGGGTGGGGAACCATCAGCGTTCGTATGTTAGTCCTCCGGCATTTTTGGTCACGGCCCTCCATGAAATACATACTAGCGTGCCATTCCGGTCAAATGGCCCTGCGAAGGATGCGGTGCGGTAAGCGTGTGGGCCATACTTGGGCAGATTGAGTTATAAGAAACAGGCAAATTGGGAACTAGTGCGGCACATGTACAGCTCGCACTTCCTGGGGGGCGACTACCGAATTCCTAGTATGTCTGAGTAGCGTACCGGGCCAGCTTTGGGTCCTCTTACCTTGTAATGGGATCGGCCTTATGGGATGCCATGACGACACTGCGGGAGGTTAATAAGTGTCCGCGATAAAGCCTCGTGGTCGAAATCTGTTACGTGCTCTTCTGTCATTTGCCATATTGGTAAAGTTCAAGAGCCACCCTATCTATTGACTCCTAGATCTCCCAAATGTATCCTCCAACAGTACTTCACCTGGATGGTAACCCCACCTCAATCACCACTTAGGTCTCCAGTACTTTTGAGCCGCCTACGCGCTCTCGAAATAAGCTAAGCTAGCTACGGTCCGTGTTAGGCGAAAAATGAATCCCTTTCCAGCGCTACCAAGTGTAGTCGGATGCGGTTGACTTATGCCTGCCCGGTGAGCAGAATTTAAATCGCTGTACCAATCAGCACTACCACAAGGCGAACGGGGCAGCCACGACTGGCGCCACAAGCATGGAAGGAGTGTCGGGCGAAATCAGGGCCGCATTAAGCCGTTTTATCACGGGTAAAGAGGTCACATGTGCACAGAGCCAGATAGTCGGCAGTGAAGGGCACAACGCTTTTTCGGCAGGAAGACCCTTGCACCTTTATCACACCGCGGGTCATCACCGGCCAAAGCAGTCGGCGGTCAACGTTAAAATTATTGCATGTCTAGGTAAAGCAGGACCAGAGAGACGTCGAAATC"
```
:::
:::


Challenge 3 consisted of using code to generate a random genome of 1500 nucleotides long. Once again, I used the `paste()` method in code to collapse it from a list down to a single string.

# Challenge 4


::: {.cell}

```{.r .cell-code}
# Challenge 4

set.seed(215)
Genome <- 100
randGenome <- sample(nucleotides, size = Genome, replace = TRUE)
randGenome <- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "TGGAATCTTTAATGTTCCGACCTTTGAGCCTCAAGTTGGACTACCGCGGCCCCCGACCGAGAGCTAACTCTAAATGATGCAAGCAGCGCGTGCCGAGTCT"
```
:::
:::


The frequency of Adenine (A) in the resulting "genome" above is 23.


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


# Challenge 5


::: {.cell}

```{.r .cell-code}
# Challenge 5 

myProduct <- 1
for(j in 1:15){
  myProduct <- myProduct * j
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


# Challenge 6


::: {.cell}

```{.r .cell-code}
# Challenge 6

Genome <- 10
randGenome <- sample(nucleotides, size = Genome, replace = TRUE)
randGenome <- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "CTGTGGACAG"
```
:::
:::

::: {.cell}

```{.r .cell-code}
myProduct <- 1
for(j in 1:15){
  myProduct <- myProduct * j
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

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


Challenge 1 involved creating a list of the four nucleotides A, C, G, and T, using the c() function.

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
 [1] "A" "C" "C" "A" "A" "A" "C" "C" "T" "T" "C" "A" "C" "G" "T"
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
[1] "ACCAAACCTTCACGT"
```
:::
:::


In challenge 2 I used code to create a random string of 15 nucleotides, titled randGenome. The `paste()` method was used to collapse the genome of nucleotides down to a single string, so it's easier to read. When I compared my collapsed genome with a classmate, I noticed that we generated very different genomes.

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
[1] "CCACATCAGCTCTTCACGGTTTTCTACCAGACATCATCCATCGTCCTAAACGGAATTAAACGCTATTCTTAAGATCACGGTCGGGTTCCGTCTCCAAGACGGAGTAACATGCTTTAGGCTCGGAGGGCTGGTCTCGGTCCAGTGTGCGGACCTGGGCCACATCCCAAAATCGATCTAACGTTCCCTGAAGGCACATCTCGACCCCAGGGTACTGTGCTGGGATCGTAGTGAAAACGAGTTGGTCACAAGTGCGTTCACCCGCCCCACAAATCGAGGAACCAGGGCAGTCATGGGACTCTGAAAGACACCCGTTAATACGCCCGCATAAGGGGTTCTTACCATCAGGCGTTAGGCGAAAAACCGAATGGGATTCCCAGACGCCACTGAGGAAATTTCCGCGGAGTCGTCATACGTTTCCTTTCTCGCTTTGCGCAACTGCGTCGAGCGGCGCTCGGAGAATACTTACGGTGCGTTCAGGGGGCAATTATGTTCAAGCAATACCATGGATTCGAGAAATCACATTTCCTCTAGTACGTAAAAGGATTGCTTCTTCTTAGTTAGGTGTTTAGACGAAATCATGAACGTAATATGAGAGTTGCTGAACGACTTACATTAACGCAATGCACGGCGGGGTTAATCTAGTCAGTAAGTATATTGCCGGTGATTCATGCCCACGGCGCAGGACTATGGTCTTGCCGCCTAAAACCAAGATCACTATAGGCAGTTGCAGAGGGATCACCGCCAGAATAATTTTGGAAACCTTCGTCAGTAGGATCATCAACTCTTAGCATGTCAAAGGATATACAGCTTACCTATCACCATGAAGCAACAGTGGGATCTTACTTGTTTTTCTTCTGACACGGGATCTTCCAGGCCTTTTACTGACAGCTATTGGACTTACGACGTGTAAATATCGACCCGTGCGCTACAGTGGCACTGAATCCCACGGTAAGCCCAAGAGGAACAATATGCAAATTATGCAATTGATATAGGGATTTAGATTCGCTACATACCAGCGTTGGGAACATCCGATGCAAATCACGCTCTTGTCGACTGGAATCCCGCAATGTGGGGGGCGTAAACTTCTACTAGTGTTGTCTCCCGGCATCTTGTCTGCGGAATAGGCTACTAGTCCCGCAAAGATTAGCCGGCGACGGGTTGGGAATCACTGCGAGCGCACCCTCCAGCCAAAAAATCTGATTTTTCCGATCCATTCATTTTTTTAACTTGGGCACTTGGGCCCTTGCTACAGCAATGAATCTGCAGACAGTGGACTCAACCTGAGGTGTTGGATTCTCTGCCGGTTCTAGAGCTGCAACCGTGTGATACATACGAAGAACCTCAGACGCACCAACCTCTGCACTGGATACATCTAGTACTGCAAAAGCCGTCATCTGCAGTTCCGATCGGGCTTTAACTCTACCGACTGCCAGGAGTCACAGTCCGGATGGTGTTTCGCAGAAAATGTCTTTAAGAAAGCCTCCCTGCCCAAAAATTTCG"
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


Challenge 3 consisted of using code to generate a random genome of 1500 nucleotides long. Once again, I used the `paste()` method in code to collapse it from a list down to a single string. I also added another line, using set.seed(215) to initialize a random number generator with the seed 215. And once again, the `paste()` function was used to collapse the list down to one single string.

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


Here, I used `set.seed(215)` to generate a random genome (`randGenome`) consisting of 100 nucleotides, collapsed down to a single string with the `paste()` function. I counted the frequency of Adenine (A) in the resulting "genome" above and got 23.

## **`for`** Loops


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


Before starting challenge 5, I began learning different ways to run a new programming technique called the `for` loop. In programming, a for loop allows us to run a set of instructions over and over for some predetermined number of iterations. Doing so will help me create loops to analyze genomes.

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


In Challenge 5, I wrote and executed my own for loop in order to analyze a genome.

# Challenge 6


::: {.cell}

```{.r .cell-code}
# Challenge 6

set.seed(215)
Genome <- 10
randGenome <- sample(nucleotides, size = Genome, replace = TRUE)
randGenome <- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "TGGAATCTTT"
```
:::
:::

::: {.cell}

```{.r .cell-code}
for(j in 1:nchar(randGenome)){
  print(str_sub(randGenome, start = j, end = j))
}
```

::: {.cell-output .cell-output-stdout}
```
[1] "T"
[1] "G"
[1] "G"
[1] "A"
[1] "A"
[1] "T"
[1] "C"
[1] "T"
[1] "T"
[1] "T"
```
:::
:::


## Flow Control

Challenge 6 involved generating a random genome substring consisting of 10 nucleotides and using the `paste()` method to collapse the genome to a single string rather than a list. Next, I wrote a `for` loop to print out each individual nucleotide instead of the entire thing. Next, I added the `1:nchar()` function to run the for loop through all nucleotides in the string. The `str_sub()` function was used to extract individual nucleotides. By using `str_sub()` and using `j` as both the start and end for subsetting, I was able to have the for loop extract each individual nucleotide.

# Challenge 7


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
[1] "AATGTTCCGA"
```
:::
:::

::: {.cell}

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

::: {.cell}

```{.r .cell-code}
countA <- 0 
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "A"){
    countA <- countA + 1
    print(countA)
  }
}
```

::: {.cell-output .cell-output-stdout}
```
[1] 1
[1] 2
[1] 3
```
:::
:::


# Challenge 8


::: {.cell}

```{.r .cell-code}
countG <- 0 
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "G"){
    countG <- countG + 1
    print(countG)
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

::: {.cell}

```{.r .cell-code}
countC <- 0 
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "C"){
    countC <- countC + 1
    print(countC)
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

::: {.cell}

```{.r .cell-code}
countT <- 0 
for(i in 1:nchar(randGenome)){
  if(str_sub(randGenome, start = i, end = i) == "T"){
    countT <- countT + 1
    print(countT)
  }
}
```

::: {.cell-output .cell-output-stdout}
```
[1] 1
[1] 2
[1] 3
```
:::
:::


## Vibrio Cholerae Chromosome DNA


::: {.cell}

```{.r .cell-code}
vib_c <- scan("VibrioCholerae.txt", what = "character", sep = NULL)
```
:::

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
 [1] "T" "G" "T" "G" "A" "T" "G" "T" "C" "C" "A" "T" "G" "A" "G"
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
[1] "TGTGATGTCCATGAG"
```
:::
:::


In Challenge 2 I used code to create a random string of 15 nucleotides, titled randGenome. The `paste()` method was used to collapse the genome of nucleotides down to a single string, so it's easier to read. When I compared my collapsed genome with a classmate, I noticed that we generated very different genomes.

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
[1] "TGTCCAATTTGATACACCCAAGTTACGATTTCGCCGAAGTACTAAACCTCTATTCCAATGATGAGCGTCTTCTCGAAGAGCATGTCCGGCGGCCAGTCCTGCATGCTCTTTTCTTAAATAAGAGCACCATCTGTATAACCCCCTCCCAAGGGGGTTATGGCAACCTTTACGGAAAAGTAAGTCTTGAGTGGTCGCTTGATCCCCTACCGACCTTGGCGGATATCTCCGCACCACAGGGAGTCCTCAGCGGAGACTCCGAGCGTAGCTAGCACATCCGTTATATGAAACCGTGAGGACCCGACAAATACGCAACCGCTACATGCAGCCTCCTACTGGAACGTTGGTTGTATGGACATTGCCAAACCTCAATCGAGGAGGGCGAAATGACCATCTAGTTGGCTCGTCAGTGTGGACCTGTACGGGATCATGCCCGTTGCTGGAACCCCCGTTCTAACAGCGAGGTTCGACTAGCCTGCGGCGGGTCCTTTTTTAGGCGAAGCTGAAATCCCACATCACCTACCACAACATGTGAGTCCCCGAGAGTTCCGCGGAAGAACACATTTAAGGCGGCAATTTGTCGGTGCCCCCGAAGAATAACCACCCCCCTTTGCACAAGTTAATCAGTGGACCATTAGTAGTAATCTCCTTAACATGTAGCGGCTTTTCGCGGCACTCCGAATGATTGCTTCTGACCAGGTCCGCCGTAGCCGGCCGGATTCTGTTACAAGTTTTGTTCTCGGGAACCGAAGGTGTGATCATCAATAAGACGCATATGTGCAATCCTGGCTACATGCCTCTCTCCAACATTAGTGACGAACTCGATAGTAAGATGTACTAGAGACCATATGCAGCTATTCTGTAAATAGTTAAGGGTACTCTGATAGATACCTTCTTCTGACGCAGGTAGGGGTAAAGCTACGGGCCATGACTGAACGGTACGTCGCCCAATCGGCGGTACGAATCCACGGGGCGGCTAACGGATAGTCGAACGGTACGTCATTGCGTGGCACACGACTTTCGTTAAGAAATTTATGTTCTGTGCCGTCCTATGGACCGGATGTCGATTGCATTATTAGCAGGCATCCTCTATTTGGGTCAAGAAATTGGTCGACGTTAGGGCGAATTCTTGATGCTTTGACGCTCAAATTTCTAGCCATCCGCACTTTATTGGTTGGGGCTCCGCATAGGTGCTAATTCTTCACTAGTCACGTGAAGAATGGCGCGGGCAATTACCGCAGCATTCCTGACTGTCACCAAGCTGCCCAGCTGTTAAGTAGTCCCTCGGATAACCATAATAACGGCCGGCCGAAAGCCGTGCCCGTCGTCAGCTCAGCCGTCAAATACTCATCGTAATCATGCTCTCACTACCATTTAGACCGAGGAGATCCTGGCGAGGCAAACCGTGCTCCACAGAAGAATCATCTAAGTGAGGCGAGGTTCTCAGGCTTCGCGCAAACACGGAAAGGTTGCGAGATTGTGGTTCGGTAGTGGTTGTTCTCA"
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


Before starting Challenge 5, I began learning different ways to run a new programming technique called the `for` loop. In programming, a for loop allows us to run a set of instructions over and over for some predetermined number of iterations. Doing so will help me create loops to analyze genomes.

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


In Challenge 7, I created a genome 10 nucleotides long using the (`randGenome`) function. I then adapted the for loop in order to count the number of Adenine (A) in randGenome. Using these functions, I was able to determine that there were 3 Adenine.

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


Challenge 8 was similar to Challenge 7 in that I created a randome nucleotide and used the for loop to count the frequencies of each of the four individual nucleotides. I then was able to perform these functions on a real genome from the *Vibrio Cholerae* chromosome DNA, consisting of 1,108,250 nucleotides. I read this large genome into R with the scan() function.

# Challenge 9


::: {.cell}

```{.r .cell-code}
countA <- 0 
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "A"){
    countA <- countA + 1
  }
}

print(countA)
```

::: {.cell-output .cell-output-stdout}
```
[1] 293942
```
:::
:::

::: {.cell}

```{.r .cell-code}
countG <- 0 
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "G"){
    countG <- countG + 1
  }
}

print(countG)
```

::: {.cell-output .cell-output-stdout}
```
[1] 256024
```
:::
:::

::: {.cell}

```{.r .cell-code}
countC <- 0 
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "C"){
    countC <- countC + 1
  }
}

print(countC)
```

::: {.cell-output .cell-output-stdout}
```
[1] 263573
```
:::
:::

::: {.cell}

```{.r .cell-code}
countT <- 0 
for(i in 1:nchar(vib_c)){
  if(str_sub(vib_c, start = i, end = i) == "T"){
    countT <- countT + 1
  }
}

print(countT)
```

::: {.cell-output .cell-output-stdout}
```
[1] 294711
```
:::
:::


In Challenge 9, I was able to use the code from Challenge 8 to count the frequency of each nucleotide in the *Vibrio Cholerae* chromosome. After doing this, the frequency of adenine was 293942, Guanine was 256024, Cytosine was 263573, and Thymine was 294711.

# Challenge 10


::: {.cell}

```{.r .cell-code}
rosalinddata <- scan("rosalind_dna.txt", what = "character", sep = NULL)
```
:::

::: {.cell}

```{.r .cell-code}
countA <- 0 
for(i in 1:nchar(rosalinddata)){
  if(str_sub(rosalinddata, start = i, end = i) == "A"){
    countA <- countA + 1
  }
}

print(countA)
```

::: {.cell-output .cell-output-stdout}
```
[1] 223
```
:::
:::

::: {.cell}

```{.r .cell-code}
countG <- 0 
for(i in 1:nchar(rosalinddata)){
  if(str_sub(rosalinddata, start = i, end = i) == "G"){
    countG <- countG + 1
  }
}

print(countG)
```

::: {.cell-output .cell-output-stdout}
```
[1] 202
```
:::
:::

::: {.cell}

```{.r .cell-code}
countC <- 0 
for(i in 1:nchar(rosalinddata)){
  if(str_sub(rosalinddata, start = i, end = i) == "C"){
    countC <- countC + 1
  }
}

print(countC)
```

::: {.cell-output .cell-output-stdout}
```
[1] 233
```
:::
:::

::: {.cell}

```{.r .cell-code}
countT <- 0 
for(i in 1:nchar(rosalinddata)){
  if(str_sub(rosalinddata, start = i, end = i) == "T"){
    countT <- countT + 1
  }
}

print(countT)
```

::: {.cell-output .cell-output-stdout}
```
[1] 201
```
:::
:::


In Challenge 10, I used code once again to scan in another genome from the rosalind website (similar to what I did in the previous challenge with the Vibrio Cholerae genome). I then used the code from Challenge 9 in order to calculate the frequency of each nucleotide in the genome string. I determined the frequency of Adenine in the Rosalind DNA genome to be 223, Guanine was 202, Cytosine was 233, and Thymine was 201. I got the Rosalind Challenge correct!

# Summary

In all, I learned a lot throughout this notebook. Including:

-   Created a list of `nucleotides`

-   Used the `sample()` function to create a random "genome" using the characters found in the `nucleotides` list.

-   Used `paste()` with the parameter setting `collapse = ""` to collapse my random genome into a single long string of nucleotides.

-   Used `set.seed()` to set a seed for a random number generator to make my results reproducible over time and across different machines (and different researchers too).

-   Used a for loop to repeat a set of simple instructions for a pre-determined number of iterations.

-   Used programmatic flow control in the form of `if/else if/else` statements to run code only when a particular condition is satisfied.

-   Constructed a `for` loop and used `if` statements to count the frequency of each of the four nucleotides in a genome string.

-   Solved a bioinformatics problem on the *rosalind* platform!

# Finding the Replication Origin, Part 1


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
genomeLength <- 2000

randGenome <- sample(nucleotides, size = genomeLength, replace = TRUE)

randGenome <- paste(randGenome, collapse = "")
randGenome
```

::: {.cell-output .cell-output-stdout}
```
[1] "CCTTTGAGCCTCAAGTTGGACTACCGCGGCCCCCGACCGAGAGCTAACTCTAAATGATGCAAGCAGCGCGTGCCGAGTCTCTGTGGACAGGATCACATTGGATGTGAGCCAAGATCTCGAGATGAAAAACAAGTAGGTTCTCTATCGCTGGCTCCAATCATTTTTATCCTTTGCTGCATACTTATGGCCCTCCAACCTTGCGAATTGCGGCATTACGTTCTATGCACGAAAGAGGCACGAGATGTATATCACTCTTCAGCTATCTGACACAGGTAGGCATTGGATGTCAGCGTACGACCGGGGTAGGCAACCCCTTCTGTTGCCCCGCTGGCCGGATGCCAAGGTGTTTTACATCGGTATTTTAAAGATGTGAACTTAAGTAACCTACTTAGCTGACGGGAAGGTGCACATGTATGTGTGACTCTACACCAAGATGCACTTAGGCATCAATAAAAGTTGCCGGTTTGTAATCCTTGACAGTAATCGAGATAATTACTTGCGGGCACATAACCTACTCGGTTCGTCCCCCTTAGCGTACGGGGGGGTGGGGAACCATCAGCGTTCGTATGTTAGTCCTCCGGCATTTTTGGTCACGGCCCTCCATGAAATACATACTAGCGTGCCATTCCGGTCAAATGGCCCTGCGAAGGATGCGGTGCGGTAAGCGTGTGGGCCATACTTGGGCAGATTGAGTTATAAGAAACAGGCAAATTGGGAACTAGTGCGGCACATGTACAGCTCGCACTTCCTGGGGGGCGACTACCGAATTCCTAGTATGTCTGAGTAGCGTACCGGGCCAGCTTTGGGTCCTCTTACCTTGTAATGGGATCGGCCTTATGGGATGCCATGACGACACTGCGGGAGGTTAATAAGTGTCCGCGATAAAGCCTCGTGGTCGAAATCTGTTACGTGCTCTTCTGTCATTTGCCATATTGGTAAAGTTCAAGAGCCACCCTATCTATTGACTCCTAGATCTCCCAAATGTATCCTCCAACAGTACTTCACCTGGATGGTAACCCCACCTCAATCACCACTTAGGTCTCCAGTACTTTTGAGCCGCCTACGCGCTCTCGAAATAAGCTAAGCTAGCTACGGTCCGTGTTAGGCGAAAAATGAATCCCTTTCCAGCGCTACCAAGTGTAGTCGGATGCGGTTGACTTATGCCTGCCCGGTGAGCAGAATTTAAATCGCTGTACCAATCAGCACTACCACAAGGCGAACGGGGCAGCCACGACTGGCGCCACAAGCATGGAAGGAGTGTCGGGCGAAATCAGGGCCGCATTAAGCCGTTTTATCACGGGTAAAGAGGTCACATGTGCACAGAGCCAGATAGTCGGCAGTGAAGGGCACAACGCTTTTTCGGCAGGAAGACCCTTGCACCTTTATCACACCGCGGGTCATCACCGGCCAAAGCAGTCGGCGGTCAACGTTAAAATTATTGCATGTCTAGGTAAAGCAGGACCAGAGAGACGTCGAAATCCATCGCCTGGTCGCCGTAATTAACGGCTCGAGTAAAACAAGATTAAACCCTGGAGCTTACATCCATAAAATTGGATGAGGGCGACGTATTCGACATCCATTCTTCTATGATGGCTAGCACAAACACCACCGGATGTACGGGCCTCCATCCTAATGTCGACGATTCGAGGTTACGTCTAAGGCTCGGCTTACCTCTCCGTGCCTCCGATTAAACGATATAAAAAGGGGAACTACACTTGTTCTTTGTATCACGATGCGTTTACCTCAATTCAATAGGCCGCTTTTCGGCGACTGCCCGCAGATACCTACAATTTGGAGCTTGAATGCAAAGCTGGCTGTTGCCGGTCGTTGCACATGTCGGACTAGTGGCGTATAATGATTGCGTGGCACTTGTGACACATCTCAATAAGCTACTGATGACTAATACTCGTCATGTTGACAGGTGATAACGAGACCGAATCGAACATTGCCGTTTGGACGATAACTCTGGCTAACAGTAACGTCTGGCCATGCGGGGCACG"
```
:::
:::

::: {.cell}

```{.r .cell-code}
nucleotide_frequency <- function(randGenome, nucleotide = "A"){
  count <- 0
  for(i in 1:nchar(randGenome)){
    if(str_sub(randGenome, start = i, end = i) == nucleotide){
      count <- count + 1
    }
  }
  return(count)
}
nucleotide_frequency("CATCGCCTGGTCGCCGTAATTAACGGCTCGAGTAAAACAAGATTAAACCCTGGAGCTTACATCCATAAAATTGGATGAGGGCGACGTATTCGACATCCATTCTTCTATGATGGCTAGCACAAACACCACCGGATGTACGGGCCTCCATCCTAATGTCGACGATTCGAGGTTACGTCTAAGGCTCGGCTTACCTCTCCGTGCCTCCGATTAAACGATATAAAAAGGGGAACTACACTTGTTCTTTGTATCACGATGCGTTTACCTCAATTCAATAGGCCGCTTTTCGGCGACTGCCCGCAGATACCTACAATTTGGAGCTTGAATGCAAAGCTGGCTGTTGCCGGTCGTTGCACATGTCGGACTAGTGGCGTATAATGATTGCGTGGCACTTGTGACACATCTCAATAAGCTACTGATGACTAATACTCGTCATGTTGACAGGTGATAACGAGACCGAATCGAACATTGCCGTTTGGACGATAACTCTGGCTAACAGTAACGTCTGGCCATGCGGGGCACGGCATGTAATTTTTGGGGACTGCATGAAATCACTTTAGGATAGTAGATTAGTACTAGTAAGGGCAGGTGACTATAGGGGCCGAGTCTCCGCAACAGTAAATGACATTAGAAGACAAGATGCAACGAGGGGTGGAGGGTCCATGAATGCAGGGCTAGTCGCTACTAGGTCGCTTCAGTAGGAAGCCTTTACTCGCTGGAGTGATAAACTAGACAGCCCACTGCGCCTGATAGCACGTACATAGGGATATGCGTTAATGGGCGCACACGAACAAGTAAACGCTAAGCACGCCCATATTTAAGCTGGCGCCGGTAGGAATATAGTAGAGGACATTCGTTGCAACCCAGTGCAATTCTCATGCATGCTGTGTTGCAACACGAAGGACCGCGCCAGTAAGGGATTCTCCGATCAAATCGTGCTTATCCGAAGCCATGTAGGGAAGCACGGAAGAACGATGGTGGGAAGAACTCATGCATCATATATCAGTTCGTTACTACCGGGGCTATAGTCGGAAAGAATTGGATAGAACCCGACCTGGTAGTGCCCTCCGGTTCTGCTCTCCGGCACGAATCGGGTAGTTCGGAAGGCATTGTTTAAGAATTACGAATATGCACCAAATTCGAGAATCTGCACCATGGCCCAAGTTACAAATCTACAGCATTGGAACCTGGGGAAAATACAAGTTTTGTGATTAGGCTGGCGCCACTCCAACAGAGTTTCGGACTCAGGATAACAACTTCAAGACGGGCCACGGATGAGGCAATCTGAAATAAGCCGCCTGTAGAGACGTAAGCTAGGCAGAGCCCTACGCGGCGAGATGTGCAAGCCCTCGTGTCCGGTCCATCGCCCCCTCCGATATATAACCAATCAAGATCAATTGTATCGCTGGTACTGCCGTGAATCCGTTAATACGCCGGGGCTCTATTTATAAAGGAGTATTTATATCCTGGGATAGCGACCGGGAAGCCAATGTATAGGGACTTAAAATTGTTTAAAGACGAGATAGAAGATAGGATGCCGATTCTTTTAATCCCATGATGGTTCCCATTCGAGATTGGGAAACAGTCAAAGGCAGGTCTGGGCGAGTCGGGGATATACGCTTGGCGCAATGGGATCGTTTTAACGTGTAGCACGCATTTCTTTACCTTTGATGAACACATAGCTGATAGCAGTAGAACTTTCCCGGTTCATGAATTATCTGGCTGCCCGAACGGAGAAAGAATGTAGTATAATCTAGTCTGATAAGGAGTTTTATAGTAAGCGTCGGCCATACATCCACGTGGTGTTTGGCCGCCGTGGTTGCATGCTGCTCACTTTTCAGAGCTCGCACTCCGGTTAACGTGTGGATCACATGGGTGGAACGATGAGCAGCGACCACGCCCAGAAATCCGCACGGAACAGCGATCAAGCGGAACACTTATGTTACCTTAGCTGTACTCGCTGATAAGGCACGGACGCCAGCAATTACTACGTTTGTGATAGA", "C")
```

::: {.cell-output .cell-output-stdout}
```
[1] 453
```
:::
:::


In the first challenge, I used the `sample()` function in conjunction with the `paste(..., collapse = "")` method to generate a random genome of length at least 2000. I then used the `nucleotide_frequency()` function to count the frequency of Cytosine in the random genome I constructed. I was able to determine that Cytosine appeared 453 times.

If I don't provide a second argument to the `nucleotide_frequency()` function, then it will count the total number of all nucleotides, not just C.

## Challenge 2


::: {.cell}

```{.r .cell-code}
rand_Genome <- function(k) { 
  nuceleotides <- c ("A", "C", "T", "G")

rand_Genome <- sample(nucleotides, size = k, replace = TRUE)

rand_Genome <- paste(rand_Genome, collapse = "")
return(rand_Genome)
}
rand_Genome (k=15)
```

::: {.cell-output .cell-output-stdout}
```
[1] "GCATGTAATTTTTGG"
```
:::
:::


In challenge 2,

## Challenge 3


::: {.cell}

```{.r .cell-code}
generate_3_mers<- function(genomeString) {
  list_3_mers <- c()
  for(i in 1:(nchar(genomeString) - 1)){
  list_3_mers <- list_3_mers %>%
  append(str_sub(genomeString, start = i, end = i + 2))
    }
  return(list_3_mers)
}
  list3mers <- generate_3_mers(rand_Genome(k=2000))
```
:::


My function collected a list of 3-mers. This function prooduced a total of 994 3-mers. It produced only 3-mers.


::: {.cell}

```{.r .cell-code}
tail(list3mers, n=25)
```

::: {.cell-output .cell-output-stdout}
```
 [1] "CCT" "CTT" "TTT" "TTA" "TAT" "ATA" "TAT" "ATC" "TCC" "CCA" "CAA" "AAA"
[13] "AAA" "AAA" "AAC" "ACC" "CCT" "CTA" "TAC" "ACG" "CGC" "GCG" "CGC" "GCA"
[25] "CA" 
```
:::
:::


If I had a list of 25 3-mers from the tail, it will contain 24 3-mers and 1 2-mer.

## Challenge 4


::: {.cell}

```{.r .cell-code}
generate_k_mers <- function(genomeString, k=3) {
  list_codon <- c()
  
  for(i in seq(1, nchar(genomeString) - k + 1, by = k)) {
  list_codon <- list_codon %>%
  append(str_sub(genomeString, start = i, end = i + k - 1))
    }
  return(list_codon)
}
generate_k_mers(rand_Genome(9))
```

::: {.cell-output .cell-output-stdout}
```
[1] "CGT" "AGT" "TTA"
```
:::
:::

::: {.cell}

```{.r .cell-code}
genomeString <- rand_Genome(15)
generate_3_mers <- function(genomeString) {
  list_3_mers <- c()
  for(i in 1:(nchar(genomeString) - 2)){
    list_3_mers <- list_3_mers %>%
      append(str_sub(genomeString, start = i, end = i + 2))
  }
  return(list_3_mers)
}
genomeString
```

::: {.cell-output .cell-output-stdout}
```
[1] "GCACTATCCTAGTGT"
```
:::

```{.r .cell-code}
generate_3_mers(genomeString)
```

::: {.cell-output .cell-output-stdout}
```
 [1] "GCA" "CAC" "ACT" "CTA" "TAT" "ATC" "TCC" "CCT" "CTA" "TAG" "AGT" "GTG"
[13] "TGT"
```
:::
:::


## Challenge 5


::: {.cell}

```{.r .cell-code}
nt_patterns <- function(string, pattern) {
  nt_matches <- 0
  
  for(i in seq(1, nchar(string))){
    if(str_sub(string, i, i + str_length(pattern)-1) == pattern){
      nt_matches = nt_matches + 1
  }
  }
  return(nt_matches)
}
nt_patterns(rand_Genome(20000), "CTG")
```

::: {.cell-output .cell-output-stdout}
```
[1] 310
```
:::
:::

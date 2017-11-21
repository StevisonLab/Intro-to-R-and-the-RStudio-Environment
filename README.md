# Calculate coverage along a chromosome:  Introduction to R and the R Studio environment
[![DOI](https://zenodo.org/badge/109879615.svg)](https://zenodo.org/badge/latestdoi/109879615)

If you are an ***instructor***, go [here](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Instructor_README.md).

If you are a ***student*** wishing to do this on your own:
1. Follow these [installation instructions](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix%201.%20Install%20R%20and%20RStudio%20Instruction.docx) for R and RStudio. 
2. Then, download the [R Studio Handout](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix%203.%20Working%20in%20R%20Studio%20Handout.pdf) to get started. This exercise should take between 30 minutes to 1.5 hours.
3. Though not required, feel free to use the accompanying [Slides for an Intro to R Studio & a Handout Review following the exercise](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix_2_Instructor_Slides.html).

### Synopsis:
This [laboratory exercise](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix%203.%20Working%20in%20R%20Studio%20Handout.pdf) is provided to introduce intermediate undergraduate students to [R](https://www.r-project.org/) and the [RStudio](https://www.rstudio.com/) environment. Abosultely NO background in R or RStudio is required! At the end of this exercise, students should be able to:

* Explain the concept of genome coverage
* Produce a quality plot of coverage along a chromosome
* Feel comfortable using and working in R and the RStudio environment

Students will also learn the importance of **reproducibility in bioinformatics research** and make a script that they can use afterwards. This resource includes a handout for students and accompanying slides for the instructor to use to preface the handout and to go over the handout after the lab activity.

### Introduction: 
R (R Core Team 2016) can be used for reading in data from other bioinformatics software, performing simple summary statistics, and plotting for the purposes of data exploration, presentations and ultimately, publication. Therefore, it is an essential tool for students to learn early in their education. RStudio (R Studio Team 2016) presents a clean interface for students to learn R in a comfortable environment. Here, I use the output of the commonly used bioinformatics software, samtools (Li et al. 2009), to assess coverage of a genomics sample (Sims et al. 2014). 

Specifically, the dataset used is mapped to the *Drosophila pseudoobscura* reference genome (Richards et al. 2005). Raw reads from a population genetics study on this species (McGaugh and Noor 2012) were downloaded and used to generate the input file. The raw reads were mapped to the reference genome using bwa (Li and Durbin 2009) and samtools (Li et al. 2009) was used to get the depth output. The [input file](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/chr4.depth.out.zip) is a combination of five contigs from the 4th chromosome, numbered sequentially as 1 to 5. This chromosome was selected as it has few contigs and simple naming conventions. I included multiple contigs to facilitate subsetting the data as part of the exercise. I further selected the first 50 kilobases of each contig to reduce the input file size. 

### Approach/Method: 

Students will learn to use RStudio and R to read in the sample dataset, perform basic functions like subsetting data and data manipulation. Students will finish by plotting the coverage along a chromosome. A [handout](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix%203.%20Working%20in%20R%20Studio%20Handout.pdf) is included to facilitate this process, with visuals for the students to follow along. Students are asked to install both R and RStudio on their individual computers prior to class (both softwares are free and cross platform compatible for PC, MAC, LINUX). Installation instructions are provided in [Appendix 1](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix%201.%20Install%20R%20and%20RStudio%20Instruction.docx).

### Core competencies: 

* Students should be able to gather and evaluate experimental evidence, including qualitative and quantitative data. 
* Students should be able to apply statistical methods when analyzing their data, and use patterns to construct a model. 
* Students should be able to generate and interpret graphs displaying experimental results. 
* Students should be able to critique large data sets and use bioinformatics to assess genetics data. 
* Students should be able to tap into the interdisciplinary nature of science.

### Appendices:

1.	[Installation Instructions](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix%201.%20Install%20R%20and%20RStudio%20Instruction.docx)
2.	[Slides for Intro to R Studio & Handout Review](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix_2_Instructor_Slides.html)
3.	[R Studio Handout](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix%203.%20Working%20in%20R%20Studio%20Handout.pdf)

### References:

>Li, H., and R. Durbin, 2009 Fast and accurate short read alignment with Burrows-Wheeler transform. Bioinformatics 25: 1754-1760.
>
>Li, H., B. Handsaker, A. Wysoker, T. Fennell, J. Ruan et al., 2009 The Sequence Alignment/Map format and SAMtools. Bioinformatics 25: 2078-2079.
>
>McGaugh, S. E., and M. A. Noor, 2012 Genomic impacts of chromosomal inversions in parapatric Drosophila species. Philos Trans R Soc Lond B Biol Sci 367: 422-429.
>
>R Core Team, 2016 R: A language and environment for statistical computing, pp.  in R Foundation for Statistical Computing.
>
>R Studio Team, 2016 RStudio: Integrated Development for R, pp. RStudio, Inc., Boston, MA.
>
>Richards, S., Y. Liu, B. R. Bettencourt, P. Hradecky, S. Letovsky et al., 2005 Comparative genome sequencing of Drosophila pseudoobscura: Chromosomal, gene, and cis-element evolution. Genome Research 15: 1-18.
>
>Sims, D., I. Sudbery, N. E. Ilott, A. Heger and C. P. Ponting, 2014 Sequencing depth and coverage: key considerations in genomic analyses. Nat Rev Genet 15: 121-132.

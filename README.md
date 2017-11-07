# Calculate coverage along a chromosome:  Introducing students to R and the R Studio environment

### Synopsis:
This [laboratory exercise](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix%203.%20Working%20in%20R%20Studio%20Handout.pdf) is provided to introduce intermediate undergraduate students to [R](https://www.r-project.org/) and the [RStudio](https://www.rstudio.com/) environment. At the end of this exercise, students should be able to:

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

### Sample/Example: 

As part of this exercise, students will output a PNG image file of their subsetted contig and customize it using the plot function in R. An example output is provided in Figure 1. This plot and the code used to generate it are provided in the handout review slides and sample code below. 

![](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Rplot.png)
>**Figure 1.** Sample output from student handout. Coverage along the subsetted contig "chr4_group5" on chromosome 4 of *D. pseudoobscura*.

Additionally, students will generate an ***RScript*** that can be used to compute coverage along a contig. Below is a sample `coverage.R` script the students should have completed by end of exercise is provided below. Each step on the handout is labeled as comments. This code can be copied directly into an R console and run to test the exercise and expected outputs. The first step must be replaced with the actual path to the provided input file on the student or instructor’s computer. See provided student handout for additional details.

```R
#2: set working directory
setwd("/path/to/file/on/students/computer") #replace with actual path!

#4a: read in data
samtools.depth=read.table(file="chr4.depth.out")

#4b
head(samtools.depth)
tail(samtools.depth)
length(samtools.depth)

#4c
length(samtools.depth$V1)

#4d
col3=samtools.depth[,3]
row19=samtools.depth[19,]
cell3_19=samtools.depth[19,3]

#4e
head(col3)
tail(row19)
length(col3)

#4f
chr4_group5=subset(samtools.depth,V1=="chr4_group5")

#4g
chr4_group2=subset(samtools.depth,V1=="chr4_group2")

#5a & b
mean(samtools.depth$V3)
sd(samtools.depth$V3)

#5c
mean(chr4_group5$V3)
sd(chr4_group5$V3)

#6a
hist(samtools.depth$V3)

#6b
hist(chr4_group5$V3)

#6c & d
plot(chr4_group5$V2,chr4_group5$V3)
plot(chr4_group5$V2,chr4_group5$V3,xlab="Position",ylab="Depth of Coverage",main="chr4_group5 Coverage",type="l",lwd=3,col="blue") #see Figure 1 plot
```

### Instructions to Instructors/TAs:

It is very important to make sure students completed the installation of both softwares correctly prior to starting the exercise. Depending on the size of the group, the sites may take a while to download and install on site. As a backup, you may choose to get the installation for all platforms on a jump drive prior to class to pass around if necessary. 

The laboratory activity should begin with a very brief introduction to the RStudio interface with the of [html slides](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix_2_Instructor_Slides.html) provided. These slides also introduce the concepts of coverage and reproducibility to the students. These slides should be presented prior to handing out the exercise.

During the ~1-1.5 hour exercise, encourage the students to work collaboratively.  Be prepared that they may go at very different paces. Encourage students who have finished to generate a plot for a different contig and compare or to continue customizing their plot. Ask what resolution, file extensions, and image sizes would be necessary for publication in a scientific journal. These extras will allow them to still feel challenged, but are not necessary for students who need a little extra time.

Finally, the html slides provided include a handout review (see contents to jump to this section). This review offers a step-by-step guide of the handout with review questions in each step. At the end of the slides, a set of resources are provided for students to learn more on their own, if so inclined.

### Appendices:

1.	[Installation Instructions](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix%201.%20Install%20R%20and%20RStudio%20Instruction.docx)
2.	[Slides for Intro to R Studio & Handout Review](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix_2_Instructor_Slides.html)
3.	[R Studio Handout](https://github.com/StevisonLab/Intro-to-R-and-the-RStudio-Environment/blob/master/Appendix%203.%20Working%20in%20R%20Studio%20Handout.pdf)

### References:

>Li, H., and R. Durbin, 2009 Fast and accurate short read alignment with Burrows-Wheeler transform. Bioinformatics 25: 1754-1760.

>Li, H., B. Handsaker, A. Wysoker, T. Fennell, J. Ruan et al., 2009 The Sequence Alignment/Map format and SAMtools. Bioinformatics 25: 2078-2079.

>McGaugh, S. E., and M. A. Noor, 2012 Genomic impacts of chromosomal inversions in parapatric Drosophila species. Philos Trans R Soc Lond B Biol Sci 367: 422-429.

>R Core Team, 2016 R: A language and environment for statistical computing, pp.  in R Foundation for Statistical Computing.

>R Studio Team, 2016 RStudio: Integrated Development for R, pp. RStudio, Inc., Boston, MA.

>Richards, S., Y. Liu, B. R. Bettencourt, P. Hradecky, S. Letovsky et al., 2005 Comparative genome sequencing of Drosophila pseudoobscura: Chromosomal, gene, and cis-element evolution. Genome Research 15: 1-18.

>Sims, D., I. Sudbery, N. E. Ilott, A. Heger and C. P. Ponting, 2014 Sequencing depth and coverage: key considerations in genomic analyses. Nat Rev Genet 15: 121-132.

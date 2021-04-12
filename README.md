# VirMC
predicting the viral sequences from metagenomic samples

VirMC: a package for predicting the viral sequences from metagenomic samples or assembled metagenomic contigs

# Version: 1.1

Authors: Kai Song

Maintainer: Kai Song ksong@qdu.edu.cn

# Description

The package provides functions to calculate the likelihoods of the reads or contigs belong to viral genomes based on a Markov Model.

# Dependencies

The python (>=2.7) are needed for the VirMC execution.

# Installation

To quick start, first download the package file VirMC.tar.bz2 according to your operating system.

For Linux user, you can install the package from the command line. Simply type the following to the command line,

> tar jxvf VirMC.tar.bz2

# Usage

(1) Calculation of the likelihood for paired-end NGS data.

As an example, the package provides two testing data sets containing 10,000 paired-end metagenomic reads in the directory of “/test_data/”.
First, you should set this directory of “VirMC” as the current directory by:

> cd VirMC

The usage is:

> python VirMC_paired-end_1.1.py input1 input2 output threshold

Arguments:

input1:  The path of the first file for paired-end NGS data;

input2:  The path of the second file for paired-end NGS data;

output:  The path and the prefix of the generated files by the script;

threshold:  The lambda threshold. The reads with lambda values larger than threshold are outputted to the file of <output>_Viral_Reads_1.fq and <output>_Viral_Reads_2.fq.

The following example which uses the test data is:

> python VirMC_paired-end_1.1.py ./test_data/test_sample_1.fq ./test_data/test_sample_2.fq ./test_sample 1.01

Output:

Two datasets were outputted by the script:

First datasets is <output>_Viral_Reads_1.fq and <output>_Viral_Reads_2.fq, which are the reads with lambda values larger than threshold.
  
Second dataset is <output>_lambda.txt, which is the lambda values for each paired-end reads.

(2) Calculation of the likelihood for assembled contigs.

The test data set of assembled contigs was also in the directory of “/test_data/”. The assembled contigs should be put in the files with fasta format. One can use the package of VirMC_contigs_1.1.py as follows:

> python VirMC_contigs_1.1.py input output threshold

Arguments:

input:  The path of the file for the assembled contigs;

output:  The path and the prefix of the generated files by the script;

threshold:  The lambda threshold. The contigs with lambda values larger than threshold are outputted to the file of <output>_Viral.fna.

The following example which uses the test data is:

> python VirMC_contigs_1.1.py ./test_data/assembled_contigs.fna ./test_data/ assembled_contigs 1.01

Output:

Two datasets were outputted by the script:

First datasets is <output>_Viral.fna, which is the reads with lambda values larger than threshold.

Second dataset is <output>_lambda.txt, which is the lambda values for each contigs.

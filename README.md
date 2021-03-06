# Notes on Dragonstar2019 @PKU (to be finished...

@PKU Beijing

2019 07.29-08.02

龙星计划笔记，主要是对各种概念的和定义的扩充学习



![](https://wx4.sinaimg.cn/mw690/695f6845ly1g5l7dvprcsj232821ib2a.jpg)

- [Day 1 Part Ⅰ Genomic technologies in disease studies](#day-1-part---genomic-technologies-in-disease-studies)
  * [1 Types of genetic variation](#1-types-of-genetic-variation)
  * [2 Revolution: single-molecule long-read sequencing](#2-revolution--single-molecule-long-read-sequencing)
    + [2.1 Oxford Nanopore Sequencing](#21-oxford-nanopore-sequencing)
    + [2.2 PacBio Single-molecule real-time (SMRT) sequencing](#22-pacbio-single-molecule-real-time--smrt--sequencing)
    + [2.3 Linked-read Sequencing](#23-linked-read-sequencing)
    + [2.4 Single-molecule optical mapping (Bionano Genomics)](#24-single-molecule-optical-mapping--bionano-genomics-)
- [Day 1 Part Ⅱ NGS data formats and variant calling](#day-1-part---ngs-data-formats-and-variant-calling)
  * [1 Basic Concepts in NGS](#1-basic-concepts-in-ngs)
  * [2 Data formats](#2-data-formats)
    + [2.1 The Rawset of Raw Data](#21-the-rawset-of-raw-data)
    + [2.2 NGS data formats](#22-ngs-data-formats)
    + [2.3 Formats use different coordinate systems, which adds confusion](#23-formats-use-different-coordinate-systems--which-adds-confusion)
  * [3 Visualization of genomic data: IGV](#3-visualization-of-genomic-data--igv)
  * [4 Coverage](#4-coverage)
  * [4.1 What is coverage?](#41-what-is-coverage-)
    + [4.2 Coverage: how many reads we need to cover the genome?](#42-coverage--how-many-reads-we-need-to-cover-the-genome-)
    + [4.3 Overdispersion](#43-overdispersion)
    + [4.4 Question on coverage](#44-question-on-coverage)
  * [5 General strategy for variant calling](#5-general-strategy-for-variant-calling)
    + [5.1 Possible Genotypes](#51-possible-genotypes)
    + [5.2 From Sequence to Genotype: Individual Based Prior](#52-from-sequence-to-genotype--individual-based-prior)
    + [5.3 From Sequence to Genotype: Population Based Prior](#53-from-sequence-to-genotype--population-based-prior)
    + [5.4 Sequence Based Genotype Calls](#54-sequence-based-genotype-calls)
- [Day 2 Part Ⅰ Alignment of short/long-read sequencing data](#day-2-part---alignment-of-short-long-read-sequencing-data)
  * [1 Sequence similarity](#1-sequence-similarity)
  * [2 Sequence alignment](#2-sequence-alignment)
    + [2.1 Pairwise alignment](#21-pairwise-alignment)
  * [3 Dynamic programming](#3-dynamic-programming)
    + [3.1 Global alignment: Needleman-Wunsch](#31-global-alignment--needleman-wunsch)
      - [3.1.1 Working of Needleman -Wunsch Algorithm](#311-working-of-needleman--wunsch-algorithm)
    + [3.2 Local alignment: Smith-Waterman](#32-local-alignment--smith-waterman)
      - [3.2.1 Working of Smith-Waterman Algorithm](#321-working-of-smith-waterman-algorithm)
  * [4 BLAST: The seed-index-map-extend-merge strategy](#4-blast--the-seed-index-map-extend-merge-strategy)
    + [4.1 BLAST Basics](#41-blast-basics)
    + [4.2 Process: The seed-index-map-extend-merge strategy](#42-process--the-seed-index-map-extend-merge-strategy)
      - [4.2.1 The Process](#421-the-process)
      - [4.2.2 Statistical significance of alignment](#422-statistical-significance-of-alignment)
  * [5  BWT](#5--bwt)
    + [5.1 Bowtie/BWA](#51-bowtie-bwa)
    + [5.2 BWT procedures](#52-bwt-procedures)
    + [5.3 BWT reverse transformation](#53-bwt-reverse-transformation)
    + [5.4 BWT search](#54-bwt-search)
- [Day 2 Part Ⅱ Genome assembly by short/long-read sequencing](#day-2-part---genome-assembly-by-short-long-read-sequencing)
  * [1 genome assembly](#1-genome-assembly)
    + [1.1 What is genome assembly](#11-what-is-genome-assembly)
    + [1.2 Why genome assembly](#12-why-genome-assembly)
    + [1.3 What types of genome assembly?](#13-what-types-of-genome-assembly-)
      - [1.3.1 *de novo* assembly](#131--de-novo--assembly)
      - [1.3.2 Comparative assembly](#132-comparative-assembly)
      - [1.3.3 *De Novo* Assembly paradigms](#133--de-novo--assembly-paradigms)
  * [2  Graph theory](#2--graph-theory)
    + [2.1 Directed graph](#21-directed-graph)
    + [2.2 Overlap-based approach (OLC)](#22-overlap-based-approach--olc-)
  * [3 Comparison of two approaches for large genomes such as human genomes](#3-comparison-of-two-approaches-for-large-genomes-such-as-human-genomes)
    + [3.1 U.S. Human Genome Project](#31-us-human-genome-project)
    + [3.2 Draft human genome](#32-draft-human-genome)
    + [3.3 How Perl Saved the Human Genome Project](#33-how-perl-saved-the-human-genome-project)
    + [3.4 Back to today](#34-back-to-today)
  * [4 Lander-Waterman statistics in genome assembly](#4-lander-waterman-statistics-in-genome-assembly)
    + [4.1 Coverage at a position can be modelled by Poisson distribution](#41-coverage-at-a-position-can-be-modelled-by-poisson-distribution)
    + [4.2 What’s the fraction of genome that are covered by reads?](#42-what-s-the-fraction-of-genome-that-are-covered-by-reads-)
    + [4.3 How many contigs are generated?](#43-how-many-contigs-are-generated-)
    + [4.4 Assembling large genomes today](#44-assembling-large-genomes-today)
    + [4.5 Canu assembler for long-read assembly](#45-canu-assembler-for-long-read-assembly)
    + [4.6 Wtdbg2 assembler for long-read assembly](#46-wtdbg2-assembler-for-long-read-assembly)
  * [5 Seven Bridges of Königsberg Problem](#5-seven-bridges-of-k-nigsberg-problem)
    + [5.1 Euler’s Theorem on directed graphs](#51-euler-s-theorem-on-directed-graphs)
    + [5.2 Euler’s Theorem on undirected graphs](#52-euler-s-theorem-on-undirected-graphs)
    + [5.3 The Königsberg graph is not Eulerian](#53-the-k-nigsberg-graph-is-not-eulerian)
    + [5.4 Hamiltonian vs Eulerian path](#54-hamiltonian-vs-eulerian-path)
  * [6 Constructing the de Bruijn Graph](#6-constructing-the-de-bruijn-graph)
    + [6.1 Error correction in de Bruijn graph](#61-error-correction-in-de-bruijn-graph)
    + [6.2 A fun hypothetical case study: Frederick Sanger’s insulin sequencing study](#62-a-fun-hypothetical-case-study--frederick-sanger-s-insulin-sequencing-study)
- [Day 3Part Ⅰ Detection of structural variants in human](#day-3part---detection-of-structural-variants-in-human)
  * [1 Human genetic variation](#1-human-genetic-variation)
  * [2 Mechanisms underlying structural variant formation](#2-mechanisms-underlying-structural-variant-formation)
    + [2.1 Recurrent structural variants](#21-recurrent-structural-variants)
    + [2.2 Nonrecurrent rearrangements](#22-nonrecurrent-rearrangements)
  * [3 Technologies for CNV Detection](#3-technologies-for-cnv-detection)
    + [3.1 Karyotyping and cytogenetic analysis](#31-karyotyping-and-cytogenetic-analysis)
  * [4 SNP genotyping arrays](#4-snp-genotyping-arrays)
  * [5 CNV Detection](#5-cnv-detection)
    + [5.1 Log R Ratio (LRR) and B Allele Frequency (BAF)](#51-log-r-ratio--lrr--and-b-allele-frequency--baf-)
    + [5.2 Detection of CNVs from SNP arrays using PennCNV](#52-detection-of-cnvs-from-snp-arrays-using-penncnv)
      - [5.2.1 PennCNV Flowchart](#521-penncnv-flowchart)
      - [5.2.2 SNP Signal Intensities](#522-snp-signal-intensities)
      - [5.2.3 Visualization of CNVs](#523-visualization-of-cnvs)
      - [5.2.4 Hidden Markov Model in PennCNV](#524-hidden-markov-model-in-penncnv)
      - [5.2.5 Copy Number States](#525-copy-number-states)
      - [5.2.6 Hidden states, copy numbers, CNV genotypes, and their descriptions](#526-hidden-states--copy-numbers--cnv-genotypes--and-their-descriptions)
  * [6 CNV Calling](#6-cnv-calling)
    + [6.1 Viterbi algorithm for calling](#61-viterbi-algorithm-for-calling)
    + [6.2 Other Types of Signal Data](#62-other-types-of-signal-data)
    + [6.3 PennCNV-Affy Pipeline](#63-penncnv-affy-pipeline)
    + [6.4 Joint Modeling on Family Data](#64-joint-modeling-on-family-data)
    + [6.5 Joint modeling of the CNVs in a trio](#65-joint-modeling-of-the-cnvs-in-a-trio)
    + [6.6 Likelihood of Signal Intensities](#66-likelihood-of-signal-intensities)
  * [7 NGS-based SV detection](#7-ngs-based-sv-detection)
    + [7.1 Read count-based methods for SV detection](#71-read-count-based-methods-for-sv-detection)
    + [7.2 Detection of SVs from discordant read pairs](#72-detection-of-svs-from-discordant-read-pairs)
    + [7.5 Detection of SVs using assembly-based methods](#75-detection-of-svs-using-assembly-based-methods)
    + [7.6 SV detection from long-read sequencing](#76-sv-detection-from-long-read-sequencing)
    + [7.7 Bionano optical mapping for SV detection](#77-bionano-optical-mapping-for-sv-detection)

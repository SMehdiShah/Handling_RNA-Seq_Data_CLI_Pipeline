# **RNA-Seq Command Line Pipeline**
## Overview
This repository provides a step-by-step guide for processing RNA-Seq data using command-line tools in Linux. The pipeline includes data retrieval, quality control, alignment, transcriptome assembly, and feature counting. It is designed for researchers and bioinformaticians who want to analyze RNA sequencing data efficiently.

## Workflow Summary
The RNA-Seq pipeline consists of several key steps:

1. Downloading Raw Data – Fetching RNA-Seq datasets from public Databases.
2. Quality Control & Trimming – Cleaning and filtering reads for better alignment.
3. Reference Genome Preparation – Downloading and indexing the genome.
4. Read Alignment – Mapping sequencing reads to the reference genome.
5. SAM/BAM File Processing – Converting and sorting alignment files.
6. Transcriptome Assembly – Constructing transcripts from aligned reads.
7. Merging Assembled Transcripts – Combining transcripts for further analysis.
8. Generating a Count Matrix – Counting mapped reads for gene expression analysis.

## Detailed Workflow

### 1. Downloading Raw Data
- RNA-Seq datasets are typically stored in public databases like the Sequence Read Archive (SRA).
- To obtain the data, the pipeline uses tools that fetch sequencing files based on specific accession IDs (e.g., SRR30802871).
- The raw sequencing files are in .sra format, which must be converted to .fastq files for processing.

### 2. Quality Control & Trimming
- The sequencing reads often contain adapter sequences, low-quality bases, or contaminants.
- A quality control step ensures that only high-quality reads are used for downstream analysis.
- The pipeline trims adapters and filters out low-quality sequences while preserving paired-end read information.

### 3. Reference Genome Preparation
- RNA-Seq data is aligned to a reference genome, which must be downloaded in FASTA format.
- The genome file is compressed and needs to be extracted before use.
- An indexing step prepares the genome for fast and efficient read alignment.

### 4. Read Alignment
- The pipeline aligns RNA-Seq reads to the reference genome using a Hisat2 tool.
- The alignment process produces a SAM (Sequence Alignment/Map) file, which stores mapped reads along with their positions in the genome.
- This step is crucial for transcript quantification and differential expression analysis.

### 5. SAM/BAM File Processing
- The SAM file is converted into a BAM (Binary Alignment/Map) file, a compressed format for efficient storage and processing.
- The BAM file is then sorted to ensure proper ordering of aligned reads, which is necessary for downstream analyses.

### 6. Transcriptome Assembly
- Assembled transcripts represent gene structures and their variations in the sample.
- The pipeline uses a transcript assembler (Stringtie) to reconstruct transcripts from aligned RNA-Seq reads.
- A reference annotation genome file in GTF format is required to guide the transcript assembly process.

### 7. Merging Assembled Transcripts
- If multiple samples or conditions are analyzed, individual transcript assemblies are merged into a single unified set.
- This step ensures consistency and allows comparison between experimental conditions.

### 8. Generating a Count Matrix
- The final step quantifies gene expression by counting the number of reads mapped to each transcript.
- A count matrix is generated, where rows represent genes and columns represent features.
- This matrix serves as input for downstream statistical analysis, such as differential expression analysis.

## System Requirements
- Linux-based operating system (Ubuntu recommended).
- Sufficient disk space for storing large sequencing files.
- At least 8GB of RAM for efficient processing.

## Software Dependencies
- SRA Toolkit – For downloading RNA-Seq datasets.
- Trimmomatic – For trimming and quality control of sequencing reads.
- HISAT2 – For aligning RNA-Seq reads to the reference genome.
- SAMtools – For processing alignment files.
- StringTie – For transcriptome assembly and merging.
- FeatureCounts (Subread package) – For generating gene expression count matrices.

## Data Requirements
- RNA-Seq dataset in FASTQ format.
- Reference genome in FASTA format.
- Annotation genome file in GTF format.

## Expected Output Files
- Trimmed FASTQ files – High-quality reads after preprocessing.
- SAM/BAM files – Alignment results.
- Sorted BAM files – Processed alignments for downstream steps.
- GTF files – Assembled transcripts.
- Merged GTF file – Unified transcriptome assembly.
- Count matrix – Table of read counts for expression analysis.

## Contributor
- **Name:** Sayed Muhammad Mehdi Shah
- **Contact Number:** +923051212120
- **Email:** mehdiacademic512@gmail.com

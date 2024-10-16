##ChIP seq##
This ChIPseq analysis was performed as an indivisual project as a part of BF528 Applications in Translational Bioinformatics course Spring 2024

ChIP seq dataset consisting of 2 paired experiments (IP and Control) derived from Mus musculus for a total of 4 samples was provided for this analysis.

##Methods##
ChIP seq samples from 2 paired experiments (IP and Control) derived from Mus musculus for a total of 4 samples were used for this experiment. Initial Quality control was performed using FastQC v0.12.0. Adapter trimming was performed using trimmomatic v0.27. Genome index was built using Bowtie2 v2.5.3 with default parameters. Align reads to the mouse primary assemble reference genome (GRCh38.p14) using Bowtie2 v2.5.3. with default parameters. Quality control of the alignment was performed using samtools v1.19.2. and compiled using MultiQC v1.21. with default parameters. BigWig files were generated using the bamcoverage utility in deeptools v2.0. with default parameters. Peak calling was performed with input as the bacground enrichment control using HOMER v4.11 with default parameters. A single list of reproducible peaks was determined using v2.31.0 with the intersections / Unions of peaks method using default parameters. Next single artifact regions from the peak lists were removed using bedtools v2.31.0. with default parameters. Peaks were annotated to their nearest genomic feature with reference to the Genome Reference Consortium Human Build 38 (hg38) using HOMER v4.11 with default parameters. Motif finding was performed to look for enrichment of known binding sequences using HOMER v4.11 with default parameters.

##Questions to Address##
Briefly remark on the quality of the sequencing reads and the alignment statistics, make sure to specifically mention the following:

Are there any concerning aspects of the quality control of your sequencing reads?
Are there any concerning aspects of the quality control related to alignment?
Based on all of your quality control, will you exclude any samples from further analysis? After QC, please generate a “fingerprint” plot (see deeptools utility) and a heatmap plot of correlation values between samples
Briefly remark on the plots and what they indicates to you in terms of the experiment After performing peak calling analysis, generating a set of reproducible peaks and filtering peaks from blacklisted regions, please answer the following:
How many peaks are present in each of the replicates?
How many peaks are present in your set of reproducible peaks? What strategy did you use to determine “reproducible” peaks?
How many peaks remain after filtering out peaks overlapping blacklisted regions? After performing motif analysis and gene enrichment on the peak annotations, please answer the following:
Briefly discuss the main results of both of these analyses and what they might imply about the function of the factor we are interested in.
Deliverables
1.Produce a heatmap of correlation values between samples.

2.Generate a “fingerprint” plot using the deeptools plotFingerprint utility

3.Create a figure / table containing the number of peaks called in each replicate, and the number of reproducible peaks

4.A single BED file containing the reproducible peaks you determined from the experiment.

5.Perform motif finding on your reproducible peaks

6.Create a single table / figure with the most interesting results Perform a gene enrichment analysis on the annotated peaks using a well-validated gene enrichment tool

7.Create a single table / figure with the most interesting results Produce a figure that displays the proportions of where the factor of interest is binding (Promoter, Intergenic, Intron, Exon, TTS, etc.)

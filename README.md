# Project8_Pharmacogenomics
Project Title: Pharmacogenomics Variants Filtering and Analysis

Overview

This project involves filtering, annotating, and analyzing pharmacogenomic variants from clinical and population datasets. The pipeline integrates clinical variant information with population-specific genomic data, providing actionable insights into variant frequency and evidence levels across populations.

Key Objectives

Filter and Annotate Variants:

Extract dbSNP variants (rsIDs) from clinical datasets.

Integrate clinical metadata (e.g., evidence levels, chemicals, phenotypes) into filtered variants.

Population-Specific Analysis:

Process VCF files to append population information to variant data.

Group variants based on population and clinical metadata.

Visualization:

Generate boxplots for variant frequency distribution by population and level of evidence.

Visualize population-specific variant occurrence.

Workflow

The workflow is split into several key steps:

Variant Extraction:

Load clinical variants (TSV format) and filter for dbSNP annotated variants (rsIDs).

Save the extracted rsIDs to a text file for downstream processing.

VCF Filtering:

Process VCF files (1000 Genomes Project) to retain only the variants matching the extracted rsIDs.

Filter variants across multiple chromosomes and save results in a compressed VCF format.

Population Annotation:

Append population-specific information to VCF files using sample IDs and population metadata.

Consolidate data for population analysis.

Clinical Metadata Integration:

Add clinical annotations (e.g., level of evidence, chemicals, phenotypes, and variant type) to the filtered variants.

Save the annotated variants in a VCF file for further analysis.

Frequency Analysis:

Analyze the occurrence of variants across populations.

Generate comprehensive tables linking variants, populations, and evidence levels.

Visualization:

Create boxplots to visualize the frequency of variants per population.

Generate separate boxplots for each level of evidence.

Input Files

clinicalVariants.tsv: Input clinical variants data with columns:

variant, gene, type, level of evidence, chemicals, phenotypes.

1000 Genomes VCF Files: Chromosome-wise compressed VCF files.

kgp3_id_pop.tsv: Mapping of sample IDs to population codes.

Output Files

dbsnp_rsids.txt: Extracted rsIDs for filtering.

Filtered VCF Files: Variants matching the dbSNP rsIDs for each chromosome.

Annotated VCF Files: VCF files with appended clinical and population metadata.

TSV Files: Tab-separated files organized by level of evidence.

Boxplots: Visualizations of variant frequency distribution per population.

Dependencies

This project uses the following Python libraries:

pandas: Data manipulation and filtering.

pysam: Processing and filtering VCF files.

matplotlib: Data visualization.

seaborn: Enhanced data visualization.

glob and os: File and directory handling.

re: Regular expressions for parsing strings.

Steps to Run the Pipeline

Setup Environment:

Install the required libraries using pip:

pip install pandas pysam matplotlib seaborn

Execute Scripts in Sequence:

Extract dbSNP variants:

Input: clinicalVariants.tsv

Output: dbsnp_rsids.txt

Filter VCF files:

Input: 1000 Genomes VCF Directory

Output: filtered VCF files.

Append population information:

Input: kgp3_id_pop.tsv, filtered VCF files

Output: VCF files annotated with population information.

Integrate clinical metadata:

Input: Annotated VCF files, clinicalVariants.tsv

Output: VCF files with clinical annotations.

Generate population tables:

Input: Combined VCF files.

Output: TSV files organized by level of evidence.

Create visualizations:

Input: all_variants_with_populations.tsv.

Output: Boxplots by population and evidence level.

View Results:

The final outputs are organized into:

Annotated VCF files

Boxplots for visualization

Consolidated TSV files by evidence level


Contact

For questions, please contact:

Name: Ilaha Husenli

Email: imusayeva3@gatech.edu

Thank you for using this pipeline for pharmacogenomic variant analysis!


# Metagenomic Intra-Species Diversity Analysis System (MIDAS)


MIDAS is an integrated pipeline that leverages >30,000 reference genomes to estimate bacterial species abundance and strain-level genomic variation, including gene content and SNPs, from shotgun metagnomes.

## Applications
1. <b>Profile bacterial species abundance</b>: rapidly estimate the abundance of 5,952 bacterial species
2. <b>Strain-level pan-genome profiling</b>: estimate the gene content of populations based on mapping to genes from reference genomes
3. <b>Single nucleotide polymorphism prediction</b>: identify single-nucleotide polymorphisms (SNPs) of populations based on mapping to reference genomes
4. <b>Phylogenetic inference</b>: reconstruct the phylogeny of strains from metagenomes and reference genomes
5. <b>Population genetic inference</b>: quantify strain-level diversity, differentiation, and selection within and between metagenomes


## Table of Contents
1. [Step-by-step tutorial](docs/tutorial.md)  
2. [Install or update MIDAS](docs/install.md)  
3. [Download default MIDAS database](docs/ref_db.md)  
4. [Build your own custom database](docs/build_db.md)
5. Scripts to run MIDAS on a single sample:
 * [Estimate species abundance](docs/species.md)
 * [Predict pan-genome gene content](docs/cnvs.md)
 * [Call single nucleotide polymorphisms](docs/snvs.md)
6. Scripts to merge MIDAS results across samples:
 * [Merge species abundance](docs/merge_species.md)  
 * [Merge gene content](docs/merge_cnvs.md)
 * [Merge SNPs](docs/merge_snvs.md)
7. Example scripts for analyzing gene content and SNPs:
 * [Strain tracking](docs/strain_tracking.md)  
 * [Population diversity](docs/snp_diversity.md)  
 * [Core-genome phylogenetic trees](docs/snp_trees.md)   
 * [Gene content dynamics](docs/compare_genes.md)


## Citation
If you use this tool, please cite:
S Nayfach, B Rodriguez-Mueller, N Garud, and KS Pollard. "An integrated metagenomics pipeline for strain profiling reveals novel patterns of transmission and global biogeography of bacteria". Genome Research 2016. doi:
10.1101/gr.201863.115

## Pipeline
<img src="images/pipeline.jpg" width="600" align="middle"/>   
<b>An integrated pipeline to estimate bacterial species abundance and strain-level genomic variation from shotgun metagnomes</b>
<sub><b>A) Metagenome species profiling.</b> Reads from a metagenomic sample are aligned against a database of phylogenetic marker genes and are assigned to species groups. Mapped reads are used to estimate the genome-coverage and relative abundance of 5,952 genome-clusters. <b>B) Metagenome pan-genome profiling.</b> A pan-genome database is dynamically constructed based on the subset of species that are present at high coverage (e.g. >1x) in the metagenome. Reads are mapped to the gene database using Bowtie2. Mapped reads are used to infer gene copy number and gene presence/absence. <b>C) Single-nucleotide variant prediction.</b> A representative genome database is constructed, as described in (B). Reads are globally aligned to the genome database using Bowtie2. Mapped reads are used to identify variants, predict consensus alleles, and estimate allele frequencies. <b>D) Merge results.</b> For each species, results are merged across one or more samples to generate several outputs, including: a gene presence/absence matrix, an allele frequency matrix, an approximate maximum-likelihood phylogenetic tree.</sub>

## Examples
<img src="images/enrichment.jpg" width="600" align="middle"/>  
<b>Comparative genomics of <i>Bacteroides ovatus</i> strains across host microbiomes</b>  
<sub> <b>A)</b> Presence or absence of genes in the <i>Bacteroides ovatus</i> pangenome across human faecal metagenomes. Column colors indicate whether a gene is core (blue; occurs in >95% of samples), auxiliary (red; occurs in 1-95% of samples ), or absent (green; occurs in < 1% of samples). <b>B)</b> Gene set enrichment analysis identifies functions overrepresented in the core genome, auxiliary genome, and genes that only occur in reference genomes.</sub>

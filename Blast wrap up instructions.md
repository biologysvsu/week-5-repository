# Blast Wrap-Up
# BLAST: Basic Local Alignment Search Tool.
The software tool finds regions of similarity between biological sequences. The program compares nucleotide or protein sequences to sequence databases and calculates the statistical significance.
---
## **Organizing Your Directories**
To keep our work organized, we will create separate directories for different BLAST runs.

1. **Create a directory for the CDS `blastn` run**:
   ```bash
   mkdir cdsblast


2. For the cds `blastx` run, make the proteinblast folder
   ```bash
   mkdir proteinblast

---
## Obtaining Input Data
We need to download reference data from the NCBI FTP server.

1. Download the CDS (Coding DNA Sequences) file:
``` bash
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/001/405/GCF_000001405.40_GRCh38.p14/GCF_000001405.40_GRCh38.p14_cds_from_genomic.fna.gz
```

2. Download Proteome (protein sequences) file from ncbi ftp
``` bash
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/001/405/GCF_000001405.40_GRCh38.p14/GCF_000001405.40_GRCh38.p14_protein.faa.gz
```
---
## Make the CDS database
1. Unzip the CDS file:
``` bash
gunzip GCF_000001405.40_GRCh38.p14_cds_from_genomic.fna.gz
```
2. Create a BLAST database from the CDS file:
``` bash
module load BLAST
makeblastdb -in GCF_000001405.40_GRCh38.p14_cds_from_genomic.fna -dbtype nucl -out cds_db
```
## Make the protein database
1. Unzip the proteome file:
``` bash
gunzip GCF_000001405.40_GRCh38.p14_protein.faa.gz
```
2. Create a BLAST database from the protein file:
``` bash
makeblastdb -in GCF_000001405.40_GRCh38.p14_cds_from_genomic.fna -dbtype prot -out protein_db
```
---
# Running BLAST Searches

## *blastn*
The blastn command compares a nucleotide query sequence to a nucleotide database.

``` bash
blastn -query my_sequence.fasta -db cds_db -out blastn_results.txt -outfmt 6
```

## *blastx*
The blastx command translates a nucleotide sequence and searches it against a protein database.
``` bash
blastx -query my_sequence.fasta -db protein_db -out blastx_results.txt -outfmt 6
```

## blastp (not running today)
The blastp command compares a protein sequence to a protein database.
``` bash
blastp -query my_protein.fasta -db protein_db -out blastp_results.txt -outfmt 6
```

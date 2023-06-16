# [High-throughput identification of human SNPs affecting regulatory element activity](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6609452/)
This repository contains the raw and processed data from the paper "High-throughput identification of human SNPs affecting regulatory element activity" (doi: 10.1038/s41588-019-0455-2). This study focuses on identifying Single Nucleotide Polymorphisms (SNPs) that affect the activity of regulatory elements in the human genome. 

## Data Description
The data are organized into four regulatory Quantitative Trait Loci (raQTL) files, each containing information about specific SNPs, their alleles, counts of DNA fragments containing these alleles, and associated expression levels and statistical comparisons in two cell lines: K562 and HepG2. 

The columns in these files are as follows:

1) 	**chr:** Chromosome on which the SNP lies.
2) 	**SNP_ID:** Identifier for the SNP.
3) 	**SNPabspos:** Genomic position of the SNP in the human genome (hg19 assembly).
4) 	**ref.element.count:** Number of DNA fragments that contain the reference (REF) allele for this SNP.
5) 	**alt.element.count:** Number of DNA fragments that contain the alternative (ALT/VAR) allele for this SNP.
6) 	**k562.ref.mean/hepg2.ref.mean:** Mean expression in K562/HepG2 cells of all DNA fragments that contain the REF allele for this SNP.
7) 	**k562.alt.mean/hepg2.alt.mean:** Mean expression in K562/HepG2 cells of all DNA fragments that contain the ALT allele for this SNP.
8) 	**k562.wilcox.p.value/hepg2.wilcox.p.value:** P-value by a Wilcoxon rank sum test in K562/HepG2 cells, comparing REF DNA fragments versus ALT DNA fragments.
9) 	**k562.wilcox.p.value.random/hepg2.wilcox.p.value.random:** Same as "k562.wilcox.p.value/hepg2.wilcox.p.value", but after shuffling the expression values of the DNA fragments.
10) **ref:** Reference allele for this SNP.
11) **alt:** Alternative allele for this SNP.

## File Description
Four raQTL files are included in this repository, each representing a unique combination of cell line (K562 or HepG2) and condition (matched control or significant ID). The file names are:

1) k562.matched.control.LP190708.txt.gz
2) k562.sign.id.LP190708.txt.gz
3) hepg2.matched.control.LP190708.txt.gz
4) hepg2.sign.id.LP190708.txt.gz

## Study Design

Sure, here's a summary in bullet format:

Identification of raQTLs
- Equalized cDNA barcode sequencing depth to minimize biases caused by differences in sequencing depth.
- Normalized SuRE signal per fragment by dividing the iPCR barcode count by the total iPCR sequencing depth for each of the 8 SuRE libraries.
- Aggregated SuRE signals by SNP allele and performed a Wilcoxon rank-sum test for each SNP, comparing the set of SSuRE values for all fragments containing the REF allele with the set containing the ALT allele.
- Defined raQTLs as SNPs with both alleles covered by 10-999 fragments, and at least one of the alleles had an S¯¯SuRE>4. They also had to meet a certain P value cutoff for a 5% False Discovery Rate.

Enrichment of raQTLs in ENCODE classes
- Determined the enrichment or depletion of raQTLs in ENCODE chromatin classes as compared to all 5.9 million SNPs assessed.

Comparison of SuRE to DNase-seq, H3K27ac, and ATAC-seq allelic imbalance
- Analyzed allelic imbalance in the DNase-seq signal by combining three available experiments and extracting the reads that overlapped a SNP found to be heterozygous in K562.
- Calculated the DNase allelic imbalance as the DNase-seq allele-ratio over the genomic allele-ratio.
- Calculated the allelic imbalance in SuRE data as the ratio of SSuRE for the REF allele over the SSuRE of the ALT allele.

Re-mapping of BACH1 and JUND ChIP-seq data
- Fastq files were downloaded from the SRA repository and reads were aligned to the human reference sequence using bowtie2.

Allele frequencies
- MAFs of SNPs were obtained from the 1000 Genomes Project.

TF motif analysis
- Identified all SNPs for which there was a difference in predicted affinity for a TF between the REF and ALT allele using SNP2TFBS.

Compiling a set of control SNPs that are matched to the significant SNPs
- Ranked all SNPs by the SSuRE of the strongest allele, the number of fragments containing the least covered allele, and the number of fragments containing the most covered allele.
- Identified the raQTLs along this ranking and selected both direct neighbors, removed the raQTLs, and down-sampled the resulting set to yield the same number of matched SNPs as raQTLs.

raQTL density around loss-of-function tolerant and loss-off-function intolerant genes
- Defined LOF-tolerant and LOF-intolerant genes, identified the corresponding TSSs, and defined regions around these TSSs of ± 100 kb.
- Determined the fraction of all SNPs that is a raQTL, and the fraction that belonged to the set of matched control SNPs.

## Contact
If you have any questions or require further clarification regarding this data, please feel free to contact the authors of the paper.

## Citation
If you use this data in your research, please cite:

```
High-throughput identification of human SNPs affecting regulatory element activity. Nature Genetics, 51(7), 1160–1169 (2019). doi: 10.1038/s41588-019-0455-2
```
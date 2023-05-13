# Geometric Omics: Graph Analysis of eQTLGen Data

Geometric Omics aims to create an analyze graph datasets based on cis-eQTL and trans-eQTL results from the eQTLGen project.

## Resources

- [eQTLGen Website](https://www.eqtlgen.org/phase1.html)
- [eQTLGen Paper](https://www.nature.com/articles/s41588-021-00913-zhttps://www.nature.com/articles/s41588-021-00913-z)

## Data Description

Data contain the following variables:

1. Pvalue - P-value
2. SNP - SNP rs ID
3. SNPChr - SNP chromosome
4. SNPPos - SNP position
5. AssessedAllele - Assessed allele, the Z-score refers to this allele
6. OtherAllele - Not assessed allele
7. Zscore - Z-score
8. Gene - ENSG name (Ensembl v71) of the eQTL gene
9. GeneSymbol - HGNC name of the gene
10. GeneChr - Gene chromosome
11. GenePos - Centre of gene position
12. NrCohorts - Total number of cohorts where this SNP-gene combination was tested
13. NrSamples - Total number of samples where this SNP-gene combination was tested
14. FDR - False discovery rate estimated based on permutations
15. BonferroniP - P-value after Bonferroni correction

## Analysis

The cis-eQTL analysis includes 19,250 genes expressed in blood, with SNP-gene combinations within 1Mb from the gene center and tested in at least 2 cohorts. The trans-eQTL analysis tests 19,960 genes expressed in blood and 10,317 trait-associated SNPs based on GWAS Catalog, Immunobase, and Astle et al. study. Trans-eQTL combinations have a distance of >5Mb and were tested in at least 2 cohorts.

The FDR calculation uses a pruned set of SNPs for trans-eQTL mapping and permutation-based FDR calculation. Crossmapping filters are applied to identify and remove potential artifacts in trans-eQTL results, recalculating the FDR afterward. Note that the full results file has not been filtered for cross-mapping effects, which may lead to artifacts in the data.

## Usage

The user should have a working knowledge of how to run Jupyter Notebooks.

## Contributing

If you'd like to contribute to the Geometric Omics project, please feel free to fork the repository and submit a pull request.

## License

This project is licensed under the MIT License.

## Contact

For any questions or concerns, please open an issue in the GitHub repository.

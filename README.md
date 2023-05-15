# Geometric Omics

Geometric deep learning toolkit for omics.

## Repo Organization

- [eQTLGen](https://www.eqtlgen.org/phase1.html)
  - The eQTLGen Consortium is a collaborative project focused on identifying the downstream consequences of trait-related genetic variants.
  - The consortium incorporates 37 datasets, with a total of 31,684 individuals.
  - The research results of the consortium, including cis-eQTL, trans-eQTL, eQTS, and replication results, are publicly available on their website.
  - The data provided by the consortium is intended for further research.
  - The consortium is made up of various cohorts and consortia, including the BIOS Consortium, The Cohort on Diabetes and Atherosclerosis Maastricht (CODAM), Genome of the Netherlands (GoNL WGS), and many others.
- [UKBB Fine-Mapping](https://docs.google.com/document/d/14LWxqlSC6hl9FtA984CQjUdFcgQQkXuffYcbXaUoqGM)
  - The study conducts statistical fine-mapping of 94 complex diseases and traits in the UK Biobank, with a focus on identifying causal common genetic variants.
  - The study involved up to 361,194 white British individuals with available phenotypes. The variants involved had an INFO > 0.8, MAF > 0.01% and HWE p-value > 1e-10.
  - Quantitative traits were transformed using inverse rank normal, with exceptions. Associations were estimated using BOLT-LMM and SAIGE.
  - Fine-mapping was done using FINEMAP and SuSiE with inputs of summary statistics, in-sample dosage LD, sample size, and variance of phenotype.
  - Post-processing involved excluding variants in the MHC region and variants with MAC < 100. Lower confidence flags were given to variants in moderate and strong LD with variants failing HWE and common structural variants respectively.

## Usage

The user should have a working knowledge of how to run Jupyter Notebooks.

## Contributing

If you'd like to contribute to the Geometric Omics project, please feel free to fork the repository and submit a pull request.

## License

This project is licensed under the MIT License.

## Contact

For any questions or concerns, please open an issue in the GitHub repository.

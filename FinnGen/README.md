# Notebooks

## Finemapping

### Background

FINEMAP and SuSiE are two computational tools used for fine-mapping GWAS data. They take different approaches to address the challenges posed by the data, as explained below:

- **FINEMAP**
  - Fully Integrated, Efficient set of Marker Accessible Probabilities (FINEMAP) is a fine-mapping tool that uses Bayesian methods.
  - The method involves computing a set of SNP configurations that are most likely to be causal.
  - FINEMAP calculates a posterior probability for each SNP configuration, representing the likelihood that the configuration is causal given the observed data.
  - The tool identifies the configuration(s) with the highest posterior probabilities as the likely causal configuration(s).
  - Advantages include accommodating multiple causal SNPs in a given locus and providing a clear measure of uncertainty through posterior probabilities.
  - However, FINEMAP can be computationally intensive, especially for large numbers of SNPs, and its accuracy depends on the assumption that the true causal configuration is among those considered.

- **SuSiE**
  - SuSiE (Sum of Single Effects) is another Bayesian approach to fine-mapping that differs from FINEMAP in its assumptions and methods.
  - SuSiE assumes that the effect of each SNP is independent and additive, which simplifies the model and enhances computational efficiency.
  - The method uses "sparse variable selection" to identify the most likely causal SNPs, starting with the assumption that most SNPs are not causal and systematically selecting SNPs that improve the model's fit to the data.
  - A key feature of SuSiE is its ability to identify "credible sets" of SNPs, which are sets of SNPs that collectively have a high posterior probability of containing at least one causal SNP. This allows researchers to identify likely regions of causal variants.

- **Comparison**
  - Both FINEMAP and SuSiE offer powerful tools for fine-mapping GWAS data.
  - The choice between them often depends on the specific requirements of the study, including the number of SNPs, the expected number of causal variants, and computational resources.

### Objective 
The goal is to create a graph neural network (GNN) model that performs binary node classification. The specific task is to predict whether variants are included after post-finemapping or not, using information from GWAS-level data.

- **Advantages of GNNs for Performing Finemapping Functionality:**

  - **Complex Relationships:**
    - GNNs are designed for graph-structured data, fitting well for modeling complex relationships in GWAS data.
    - Genetic variants often do not act independently due to linkage disequilibrium (LD). GNNs can represent each variant as a node and the correlation between them as edges, naturally modeling the LD structure.

  - **Efficiency and Scalability:**
    - Traditional fine-mapping tools like FINEMAP and SuSiE can be computationally intensive, especially with large numbers of SNPs.
    - GNNs can efficiently process large-scale genomic data, potentially making them more scalable for large GWAS datasets.

  - **Incorporation of Additional Data:**
    - GNNs can incorporate other types of data in addition to genetic variants, such as gene expression data or functional annotations.
    - This could potentially improve the power to detect associations and the accuracy of the post-finemapping classification task.

  - **Predictive Power:**
    - GNNs have demonstrated strong predictive power in many applications.
    - For binary node classification tasks, this could translate into accurate predictions of whether variants are included after post-finemapping.


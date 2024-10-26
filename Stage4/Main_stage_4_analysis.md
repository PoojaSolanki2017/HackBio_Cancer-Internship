<!--StartFragment-->

**HackBio Stage 4 Task Report**

**Aim:** Differential Expression Analysis to distinguish any 2 IDH classes and Unsupervised clustering of gliomas based on methylation levels to classify the six IDH statuses 

**Authors:** Pooja Solanki (@poojasolanki2024), Mahima Chakraborty (@mahima\_ch), Mariam Mohamed (@Mariam000v), Nourhan Saad (@Nourhan-25), Mercy Ade Ige (@MaiStar), Tamosree Sikder (@Tamosree), Osama Shukri (@Osama)

**Link to the research paper:** <https://www.cell.com/cell/fulltext/S0092-8674(15)01692-X> 

**Introduction to gliomas, IDH status, and their significance:**

Gliomas, a common type of brain tumor originating from glial cells, are classified based on the glial cell type they arise from and their grade, ranging from slow-growing lower grades (I and II) to aggressive higher grades (III and IV), with grade IV resembling glioblastoma, the most severe form. Diffuse gliomas are particularly challenging due to their invasive nature, making them difficult to treat and prone to recurrence. A key biomarker in glioma classification is the IDH (Isocitrate Dehydrogenase) gene mutation, which plays a critical role in the tumor's behavior and prognosis.

The 2021 WHO classification of brain tumors emphasizes the importance of IDH mutations in gliomas. IDH-mutant gliomas are often found in younger patients, progress slowly, and are linked with better outcomes, while IDH-wildtype gliomas are more aggressive, often associated with glioblastomas. IDH status not only influences prognosis but also guides therapeutic strategies, as targeting IDH mutations with specific inhibitors shows promise in exploiting the vulnerabilities created by these mutations.

**Description of the dataset and preprocessing steps:**

TCGA project link for Gliomas LGG -  <https://portal.gdc.cancer.gov/projects/TCGA-LGG>

RNA-Seq data for low-grade gliomas (LGG) and corresponding metadata, including IDH status, were obtained using the TCGAbiolinks R package with the project code "TCGA-LGG." The data, selected from the "Transcriptome Profiling" category, used the "STAR - Counts" workflow type for uniform processing, resulting in a total of 516 samples. The dataset was aligned by matching sample identifiers in the raw RNA-Seq count matrix (DEA\_matrix) and associated metadata (DGE\_metadata). 

Preprocessing involved normalizing the raw counts using the TCGAanalyze\_Normalization function, which adjusts for gene length and sequencing depth biases. Lowly expressed genes were filtered out using a quantile cutoff of 0.25 through the TCGAanalyze\_Filtering function, retaining only genes with sufficient expression levels. The data was then log2-transformed, with a pseudocount of 1 added to avoid log transformation issues with zero values. This cleaned, normalized dataset was prepared for differential expression analysis.

**Differential Expression Analysis results** 

This analysis aimed to identify differentially expressed genes in glioma using TCGA data. The volcano plot highlights genes with significant expression changes, with upregulated genes indicated in red and downregulated ones in blue. Notable genes include ENSG00000257935 and ENSG00000286953, which are associated with the mutant IDH status, showing substantial upregulation, suggesting their potential roles in glioma progression and adaptation to IDH mutations. Conversely, the wild-type IDH genes ENSG00000204542 and ENSG00000228630 exhibit significant downregulation, indicating that their reduced expression in mutant samples may contribute to tumor development. The heatmap further confirms distinct expression patterns between mutant and wild-type samples, showcasing clear clustering based on IDH status. Overall, these results highlight key genes that may serve as potential biomarkers or therapeutic targets in glioma management.

**Methodology for implementing and applying the KNN algorithm**

**Data Acquisition and Preprocessing**

The TCGAbiolinks package was utilized to extract RNA-Seq data from the TCGA-LGG project. Data preparation involved selecting the 8000 genes with the highest variability. Subsequently, the DESeq2 method was employed for normalization to address differences in library size, and genes exhibiting high correlation were eliminated to minimize redundancy.

**Model Training and Evaluation**

The dataset, after preprocessing, was divided into two subsets: 70% for training and 30% for testing, utilizing the createDataPartition function. A Random Forest algorithm, implemented through the ranger package, was used to train a classifier on the training data. To reduce bias and improve the model's ability to generalize, 7-fold cross-validation was incorporated during the training process. The model's effectiveness was then assessed by applying it to the test set. To evaluate the accuracy of IDH mutation status predictions, a confusion matrix was constructed.

**Results of the kNN, including visualizations and evaluation metrics as presented in the paper**

The Random Forest algorithm demonstrated strong efficacy in classifying IDH mutation status among lower-grade glioma (LGG) patients. Analysis of the separate test set using a confusion matrix revealed high accuracy, suggesting excellent predictive performance. The model's ability to discriminate can be depicted through a Receiver Operating Characteristic (ROC) curve, which shows the balance between sensitivity and specificity. Additionally, a thorough assessment of the model's performance was conducted using various metrics, including precision, recall, and F1-score, offering a detailed evaluation of its effectiveness in identifying both positive and negative instances. These results indicate that the Random Forest model could have significant clinical applications for accurately and reliably predicting IDH mutation status in LGG patients, potentially enhancing personalized treatment approaches.

**Comparison with the findings reported in the target paper. (Do you think we need more clusters based on newer datasets)**

The current analysis aligns with the findings in the target paper, emphasizing that IDH mutations define a distinct glioma subgroup with favorable outcomes, especially in the context of LGGs. The data shows that IDH-mutant gliomas exhibit unique gene expression patterns and a hypermethylation phenotype (G-CIMP), consistent with the literature. The observed upregulation and downregulation of specific genes tied to IDH mutation status confirm the classification and its prognostic relevance. However, while the analysis successfully distinguishes between IDH-mutant and wild-type subgroups, further clustering based on newer datasets or additional genetic markers (e.g., TERT promoter mutations) may refine these classifications and enhance the predictive accuracy.

Also incorporating more clusters based on newer datasets could enhance our understanding and classification of gliomas. The current classification approach, while effective in distinguishing IDH-mutant and wild-type gliomas, may be limited in its ability to capture the full complexity of tumor biology, especially with respect to other genetic mutations such as TERT promoter mutations and 1p/19q co-deletion status.

**Conclusion and insights gained from the analysis** 

This analysis confirms the critical role of IDH status in glioma classification and prognosis, reinforcing its value as a biomarker in clinical settings. IDH mutations correlate with distinct gene expression patterns and favorable outcomes, underscoring the potential for targeted therapies that exploit these genetic vulnerabilities. Additionally, the use of Random Forest models demonstrated high efficacy in predicting IDH mutation status, suggesting that machine learning approaches could be instrumental in refining glioma diagnostics and enhancing personalized treatment plans.

****

**References**

1. Memorial Sloan Kettering Cancer Center. (n.d.). Types of Glioma. Retrieved from https\://www\.mskcc.org/cancer-care/types/glioma/types-glioma

2. Antonelli, M., & Poliani, P. L. (2022). Adult-type diffuse gliomas in the new 2021 WHO Classification. Pathologica, 114(6), 397.

3. Onizuka, H., Masui, K., & Komori, T. (2020). Diffuse gliomas to date and beyond: The 2016 WHO Classification of Tumours of the Central Nervous System. International Journal of Clinical Oncology, 25(6), 997–1003. https\://doi.org/10.1007/s10147-020-01695-w

4. Kayabolen, A., Yilmaz, E., & Bagci-Onder, T. (2021). IDH mutations in glioma: A double-edged sword in clinical application. Biomedicines, 9(7), 799. https\://doi.org/10.3390/biomedicines9070799

5. Alshiekh Nasany, R., & de la Fuente, M. I. (2023). Therapies for IDH-mutant gliomas. Current Neurology and Neuroscience Reports, 23, 225–233. https\://doi.org/10.1007/s11910-023-01265-3

<!--EndFragment-->

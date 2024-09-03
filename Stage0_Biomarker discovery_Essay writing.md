<!--StartFragment-->

## **Biomarker discovery using differential expression analysis**


**Introduction**

Bioimarker is the presence of any substance or indicator that can diagnose or prognose a disease, an infection or an environmental exposure\[1]. There are many different forms of biomarkers that can be observed. For example, blood pressure, body mass index or the presence of some particular genes, proteins or chemicals in body fluids. These all are types of biomarkers\[2]. Biomarkers could be detected and measured by various techniques. However, in this essay we will discuss how **differential expression** of genes could help to discover these biomarkers. 

**Discussion**

Differential expression means how genes are regulated to produce RNA molecules. Every cell in our body contains the same genome but why some genes are only expressed in the eye cells while others in stomach cells\[3]. This mechanism is called differential gene expression \[3], and the amount of RNAs produced by the particular gene decides whether the gene is upregulated or downregulated. If the number of RNA is more then the gene is upregulated and if it is less or null then it is downregulated\[4]. 

This differential gene expression can be measured by RNA-Seq data analysis method \[4]. Basically, in the RNA-Seq experiment a tissue or a cell is treated with chemicals or drugs for which we want to see the reaction on gene expression level. Then, we compare the gene expression level between treated samples and control samples\[4]. For example, if we want to detect that a particular biomarker or gene is expressed or not after treating it with certain cancer treatment drugs, we can know it by comparing its gene expression level from the control and treated sample groups. 

Thus, after the treatment with particular chemicals, RNA molecules are extracted from such samples and converted into cDNA libraries. Once sequencing is done, FASTQ files are generated. After that various steps are performed, including quality analysis, trimming of adapters, aligning with reference genome, and at last generation of a feature count matrix. This matrix is a file which gives the total count of transcripts per gene. The analysis of this count matrix can be visualised by drawing different types of plots with the help of R language packages such as EdgeR and DeSeq2 \[4]. 

**Conclusion**

Biomarkers are different forms of indicators which help to identify the diagnosis or prognosis of some disease, condition or environmental changes in an organism. The discovery of these markers can be done by measurement of differential gene expression analysis using techniques like RNA-Seq. This technique uses various bioinformatics tools and R packages to measure this expression and find results. 


**References**

1. _Biomarkers_. (n.d.). National Institute of Environmental Health Sciences. https\://www\.niehs.nih.gov/health/topics/science/biomarkers
   
2. _7 Types of Biomarkers_. (n.d.). www\.atlasantibodies.com. https\://www\.atlasantibodies.com/knowledge-hub/blog/7-types-of-biomarkers/?language=en
   
3. Gilbert SF. Developmental Biology. 6th edition. Sunderland (MA): Sinauer Associates; 2000. Differential Gene Expression. Available from: <https://www.ncbi.nlm.nih.gov/books/NBK10061/>
   
4. Pola-Sánchez E, Hernández-Martínez KM, Pérez-Estrada R, Sélem-Mójica N, Simpson J, Abraham-Juárez MJ, Herrera-Estrella A, Villalobos-Escobedo JM. RNA-Seq Data Analysis: A Practical Guide for Model and Non-Model Organisms. Curr Protoc. 2024 May;4(5):e1054. doi: 10.1002/cpz1.1054. PMID: 38808970.

<!--EndFragment-->

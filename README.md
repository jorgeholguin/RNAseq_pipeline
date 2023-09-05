# A pipeline to analyze RNAseq data from the NCI-GDC

Here we will determine whether patients with misssense mutations in the autoinhibitory helix of PPP3CA (catalytic subunit of the calcineurin phosphatase) have altered transcriptional signatures compared to patients with missense mutations in PPP3CA but outside its autoinhibitory helix. Protein autoinhibition is a prevalent mechanism for the control of protein function and mutations that alter autoinhibition are common in cancer driver genes. PPP3CA is not yet categorized as a cancer driver, but mutations within its autoinhibitory helix could be cancer promoting. This is due to the regulatory role that calcinuerin exerts on the NFAT transcription factors, which are known to be misregulated in several cancer types.

**Summary of the pipeline**

1. Download the STAR Counts data from the NCI-GDC database
2. Remove samples with small library sizes
3. Filter out lowly expressed genes
4. Perform some exploratory data analyses using PCA and heatmaps
5. Estimate sources of unwanted variation using `svaseq`
6. Perform the differential gene expression analysis using `DESeq2`
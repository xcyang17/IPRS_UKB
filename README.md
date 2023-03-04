# IPRS: Imaging Polygenic Risk Scores in UK Biobank

IPRS is a project for the development and sharing of polygenic risk scores for 4,206 brain imaging-derived phenotypes for 400,000 [UK Biobank](https://www.ukbiobank.ac.uk/) subjects not participating in the imaging study. 

## Overview
UK Biobank (UKB) brain imaging data are extremely useful for a wide range of clinical research and applications. However, due to the cost and difficulty of obtaining data, the UKB imaging study will be limited to 100,000 participants, leaving the majority (80%) of half a million UKB subjects without imaging data. Because imaging-derived phenotypes (IDPs) are heritable and genetic information is available for most UKB subjects, genetic data can predict IDPs for UKB subjects outside of the imaging study. 

Here we systematically develop and evaluate biobank-scale genetic polygenic risk scores (PRS) for 4,206 IDPs from multiple brain imaging modalities and processing pipelines. The majority of IDPs (64.76%, 2,774/4,206) were significantly predicted by PRS developed by subjects with both genetic and imaging data. Moreover, genetically predicted IDPs detected associations with a wide variety of complex traits and diseases, with the patterns being consistent across different imaging pipelines. 

Our results suggest that genetic prediction through PRS may provide an economical and practical solution to make the UKB imaging study more beneficial to a broader population. Our PRS data resources have been made publicly available through [Zenodo](https://zenodo.org/) and will be returned to the UK Biobank. 


## Website
...?


## Tutorial
### Individual-level PRS generation
The individual-level PRS can be generated using our shared PRS weights at [Zenodo](https://zenodo.org/) via [PLINK 2.0](https://www.cog-genomics.org/plink/2.0/). The following is an example

```{bash}
$ plink \
    --bfile PATH_TO_BFILE_WITHOUT_EXTENSION \
    --score PATH_TO_PRS_WEIGHTS \
    --out PATH_TO_OUTPUT_WITHOUT_EXTENSION
```
where `PATH_TO_BFILE_WITHOUT_EXTENSION` is the path to the bfiles (`bim,bed,fam`) without the extensions, `PATH_TO_PRS_WEIGHTS` is the path to our shared PRS weights, and `PATH_TO_OUTPUT_WITHOUT_EXTENSION` is the desired path for the individual-level PRS. 




## Data Availability
PRS-CS weight of brain MRI traits can be freely downloaded at [Zenodo](https://zenodo.org/). The individual-level data used in this study can be obtained from https://www.ukbiobank.ac.uk/.







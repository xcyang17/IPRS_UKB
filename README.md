# IPRS: Imaging Polygenic Risk Scores in UK Biobank

IPRS is a project for the development and sharing of polygenic risk scores (PRS) for 4,206 brain imaging-derived phenotypes for 400,000 UK Biobank subjects not participating in the imaging study. 


## Overview
UK Biobank (UKB) brain imaging data are extremely useful for a wide range of clinical research and applications. However, due to the cost and difficulty of obtaining data, the UKB imaging study will be limited to 100,000 participants, leaving the majority (80%) of half a million UKB subjects without imaging data. Because imaging-derived phenotypes (IDPs) are heritable and genetic information is available for most UKB subjects, genetic data can predict IDPs for UKB subjects outside of the imaging study. 

Here we systematically develop and evaluate biobank-scale genetic polygenic risk scores for 4,206 IDPs from multiple brain imaging modalities and processing pipelines. The majority of IDPs (64.76%, 2,774/4,206) were significantly predicted by PRS developed by subjects with both genetic and imaging data. Moreover, genetically predicted IDPs detected associations with a wide variety of complex traits and diseases, with the patterns being consistent across different imaging pipelines. 

Our results suggest that genetic prediction through PRS may provide an economical and practical solution to make the UKB imaging study more beneficial to a broader population. Our PRS data resources have been made publicly available through [Zenodo](https://zenodo.org/) and will be returned to the UK Biobank. 


## Tutorial
### Individual-level PRS generation
The individual-level PRS can be generated using our shared PRS weights at [Zenodo](https://zenodo.org/) via [PLINK 2.0](https://www.cog-genomics.org/plink/2.0/). The following is an example
```{bash}
$ plink \
    --bfile PATH_TO_BFILE_WITHOUT_EXTENSION \
    --score PATH_TO_PRS_WEIGHTS 2 4 6 \
    --out PATH_TO_OUTPUT_WITHOUT_EXTENSION
```
where `PATH_TO_BFILE_WITHOUT_EXTENSION` is the path to the genotyping data in the PLINK binary format ({`bim,bed,fam`}) without the extensions, `PATH_TO_PRS_WEIGHTS` is the path to our shared PRS weights, and `PATH_TO_OUTPUT_WITHOUT_EXTENSION` is the desired path for the individual-level PRS. `2 4 6` indicates that the 2nd column of `PATH_TO_PRS_WEIGHTS` contains rs ID, the 4th column of `PATH_TO_PRS_WEIGHTS` contains the allele codes (A1), and the 6th column of `PATH_TO_PRS_WEIGHTS` contains the effect size estimates. See details about PLINK linear scoring [here](https://www.cog-genomics.org/plink/2.0/score).


## Methods
Here we provide some more details about the development of the PRS weights.
### Imaging traits
The data used in our study was obtained from the UK Biobank (UKB) study, which recruited around 500,000 individuals between the ages of 40 and 69 between 2006 and 2010 (https://www.ukbiobank.ac.uk/). The ethics approval of the UKB study was obtained from the North West Multicentre Research Ethics Committee (approval number: 11/NW/0382). We obtained a total of 4,206 brain imaging-derived phenotypes (IDPs) from the UKB study (http://www.ukbiobank.ac.uk/resources/), which consisted of 301 [BIG-KP](https://bigkp.org/) brain imaging traits and 3,905 [UKB-Oxford](https://open.win.ox.ac.uk/ukbiobank/big40/) brain imaging traits.

The BIG-KP brain imaging traits consist of three imaging modalities: 
- Regional brain volumes, 101 traits
- Tract-averaged diffusion tensor imaging (DTI) parameters, 110 traits
- Resting fMRI traits (activity and functional connectivity), 90 traits.

The UKB-Oxford imaging traits consist of four imaging modalities and a number of sub-modalities:
- Structural MRI (sMRI), 1437 traits
* FIRST ([Category 1102](https://biobank.ctsu.ox.ac.uk/crystal/label.cgi?id=1102)), 15 traits
* FAST ([Category 1101]()), 139 traits
* Freesurfer ASEG ([Category 190]()), 95 traits
* Freesurfer BA exvivo ([Category 195]()), 84 traits
* Freesurfer a2009s ([Category 197]()), 444 traits
* Freesurfer DKT ([Category 196]()), 186 traits
* Freesurfer desikan gw ([Category 194]()), 70 traits
* Freesurfer desikan pial ([Category 193]()), 66 traits
* Freesurfer desikan white ([Category 192]()), 202 traits
* Freesurfer subsegmentation ([Category 191]()), 121 traits
* Regional T2* ([Category 109]()), 14 traits
* white matter hyperintensity volume ([Category 112]()), 1 trait
- Diffusion MRI (dMRI), 675 traits
    * TBSS ([Category 134]()), 432 traits
    * ProbtrackX ([Category 135]()), 243 traits
- Task fMRI (tfMRI) ([Category 106]()), 16 traits
- Resting fMRI (rfMRI) ([Category 111](https://biobank.ndph.ox.ac.uk/showcase/label.cgi?id=111)), 1777 traits
* ICA-based rfMRI activity, 76 traits
* ICA-based rfMRI connectivty, 1701 traits


We obtained the PRS weights by 

applying the [PRS-CS method](https://github.com/getian107/PRScs) 




## Website
...?






## Data Availability
Our PRS-CS weight of brain MRI traits can be freely downloaded at [Zenodo](https://zenodo.org/). The individual-level genotyping data used in this study can be obtained from https://www.ukbiobank.ac.uk/.




## References
...


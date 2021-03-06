---
title: "UK BioBank - Department of Psychiatry"
author: "Richard A.I. Bethlehem & Varun Warrier"
e-mail: rb643 [at] medschl.cam.ac.uk
---
Table of Contents
=================

   * [About the UK BioBank](#about-the-uk-biobank)
      * [How to access this resource](#how-to-access-this-resource)
      * [Authorship, usage and acknowledgements](#authorship-usage-and-acknowledgements)
   * [Main Project Description](#main-project-description)
   * [Data management](#data-management)
      * [Code sharing](#code-sharing)
      * [Phenotypic data](#phenotypic-data)
      * [File and folder structure for imaging data](#file-and-folder-structure-for-imaging-data)
      * [Structural imaging](#structural-imaging)
         * [Freesurfer reconstruction](#freesurfer-reconstruction)
         * [Structural Parcellation](#structural-parcellation)
      * [Functional imaging](#functional-imaging)
         * [Functional Parcellation](#functional-parcellation)
      * [Diffusion weighted imaging](#diffusion-weighted-imaging)
         * [Diffusion Parcellation](#diffusion-parcellation)
      * [Genetics](#genetics)
   * [Planned](#planned)
   * [Ongoing projects](#ongoing-projects)
   * [Publications](#publications)


# About the UK BioBank
The UK BioBank (UKB) provides a unique, large and comprehensive dataset that includes both extensive phenotypic information as well as neuroimaging and genetics. We are aware that there are several groups within the Departments of Psychiatry, Psychology and Clinical Neurosciences interested in using this resource. To minimize redundancy in both UKB applications as well as the use of computational and data storage resources we here outline some of the potential ways in which this data might be accessed by people within the Department. We outline the fixed data structure and available data-formats that we hope may be of use to others. Furthermore, some already planned processing and added sub-projects are provided as examples.

Please note that we provide data as is. That means we do not take responsibility for (re-)running specific processing pipelines when software updates become available (or when a reviewer requests it). That being said, we are of course alway open to have a discussion for specific requests if you think particular processing pipelines can be of interest to the wider research community.

Finally, we strongly encourage others in the Department to share in this resource so please feel free to get in touch with us and/or distribute this white paper draft to other within the Department you think might be interested.

Richard A.I. Bethlehem (rb643)    
Varun Warrier (vw260)      

## How to access this resource
Accessing this data resource is currently done on a case by case basis, but where possible we would like to prevent having duplicates of a large dataset sitting on the server nor do we want people to redo things that someone else has already done. Thus to access this data:

You can put in your own application. Again in order to maximize efficiency we would still encourage you to use data that is already there. If your proposal is approved by the UKB there is an option to link your application to an existing one and use the same dataset and link the subject identifiers. This is the preferred option by the UK BioBank and it also ensures you have maximum ownership and flexibility over your applications data outside the imaging and genetics data already stored. If you are planning an application we strongly encourage you to get in touch during the application stage and make clear at application stage that you want to use existing data held at your institute.


## Authorship, usage and acknowledgements

If you are using the existing variables available from the UK Biobank, you do not need to include anyone as co-authors. However, if you are using variables generated by others (for example imaging metrics processed using specific pipelines, polygenic scores, bespoke phenotypic variables), please contact the person who has generated the variables before using them. Please check with them re. authorship in accordance with the University's authorship guidelines (see: http://www.medschl.cam.ac.uk/wp-content/uploads/2014/02/CoS14_68-Authorship_Code_of_Practice-FINAL.pdf?04c0fc). If you are unsure if variables were generated by a specific user or were UKB default please contact Varun or Richard to check.

If you are creating a new variable and would like to make it available for others to use please include the following:    
1. A readme file with the description of the variables, your name and contact information, and details of use   
2. A file, or a link to a webpage (github, OSF etc) with detailed methods you used for generating the variables including the code.    

Finally, when making use of this resource please acknowledge the following funding sources that continue to make storage and processing of this dataset possible in your publications:

"This research was co-funded by the NIHR Cambridge Biomedical Research Centre and a Marmaduke Sheild grant to Richard A.I. Bethlehem and Varun Warrier The views expressed are those of the author(s) and not necessarily those of the NHS, the NIHR or the Department of Health and Social Care."

# Main Project Description
Structural changes in the brain contribute to cognitive processes and neuropsychiatric conditions. Numerous imaging and lesion studies have identified specific anatomic regions that are involved in discrete neural processes. Pathological abnormalities in neural structures contribute to neuropsychiatric conditions. Neural networks (structural or resting state) of the brain represent a promising set of endophenotypes for a range of neuropsychiatric conditions. Discrepancies in both global and local characteristics of neural networks have been implicated in a wide number of psychiatric conditions including autism, schizophrenia, and major depressive disorder (Hullshof Pol and Bullmore., 2013). As such, they represent promising intermediary phenotypes that can potentially link genetics and molecular mechanisms of pathology with broader cognitive and behavioural abnormalities observed in individuals with neuropsychiatric conditions. A few studies report that both global and local network properties influence cognition and intelligence.

Twin studies have identified that different neural graph metrics have low to modest heritability. For example, the largest study to our knowledge, identified heritabilities ranging from 0 - 64% for a number of graph metrics (Sinclair et al., 2015). These are similar to what has been observed in a number of neuropsychiatric conditions and psychological traits, suggesting that, as a phenotype, neural network properties can lend themselves to genetic investigations. In addition, it has recently been shown that effective connectivity within the default mode network (DMN; Xu et al.,  2016) had an estimated heritability of 0.54 in a group of 46 twins.

However, a large-scale investigation of the genetic contribution to these neural networks has not been thus far undertaken. The UK Biobank is an ideal resource to conduct this investigation. The homogeneity of neuroimaging and genotyping methods reduces the number of potential confounding factors that are likely to be present in other meta-analysis of imaging-genetics studies. Here, using both structural and functional imaging, we propose to extract specific network metrics, correlate them to phenotypes in participants, conduct genome-wide association analyses, establish additive SNP based heritability, and identify genetic correlations between various metrics and neuropsychiatric conditions, and psychological and cognitive traits. In addition, we will generate polygenic scores to investigate if these can be used to predict neuropsychiatric phenotypes and subtypes within them. Finally, we will also investigate differences in these neural networks attributable to socio-demographic factors including education, age, and sex.

# Data management
All data is currently stored on the HPC and can be made available in read-only format to interested researchers that have approved projects. We strongly discourage creating local copies of this dataset as that will rapidly clog-up the server resources we all share.

The HPC presently contains structural (T1, T2-FLAIR, DWI and SWI) and functional (task and rs-fMRI) imaging data on /rds/project/rb643/rds-rb643-ukbiobank2/ for approximately 38000 subjects. Currently data has been pre-processed using the standard UKB pre-processing pipelines found [here](https://biobank.ctsu.ox.ac.uk/crystal/crystal/docs/brain_mri.pdf) as well as the standard freesurfer structural pre-preprocessing. Please note that ICA denoising has not been completed for all subjects.

## Code sharing
Code used in extracting or analysing data from UK BioBank is made available on this GitHub. This code can be referenced in publications and is available for everyone to use.

## Phenotypic data
A full overview of all variables in the current application can be found [here](/ukb41432.html).

## File and folder structure for imaging data
Although the UK BioBank does not provide data in BIDS format we aimed to stay as close to the same format as possible. At the moment the structural and functional data are provided for each subject in the **anat** and **func** subdirectories. See below for an overview of the standard file and folder structure.

```{r, echo=TRUE}
# ~/Data_Imaging/  
#               .../subID/  
#                   .../anat/  
#                       .../T1  
#                           .../T1_brain.nii.gz  
#                           .../T1_unbiased_brain.nii.gz
#                           .../T1_fast
#                               .../T1_brain_seg.nii.gz   
#                           .../T1_first/
#                               .../T1_first_all_fast_firstseg.nii.gz  
#                       .../T2_FLAIR
#                           .../T2_FLAIR.nii.gz
#                           .../T2_FLAIR_unbiased_brain.nii.gz
#                       .../SWI
#                   .../DWI
#                       .../DWI/parcellations/
#                               .../aparc_seq
#                                   .../MD.txt
#                                   .../FA.txt
#                               .../500_aparc_seq
#                               .../HCP.fsaverage
#                               .../sjh
#                       .../DWI/dMRI/
#                       .../.../dMRI/dti_FA.nii.gz
#                       .../.../dMRI/dti_MD.nii.gz
#                       .../.../dMRI/NODDI...nii.gz
#                           .../...
#                   .../surfaces/  
#                       .../subID/
#                           .../label/
#                           .../mri/
#                           .../stats/
#                           .../parcellation/
#                           .../...
#                   .../func/  
#                       .../fMRI  
#                           .../rfMRI.nii.gz
#                           .../rfMRI.ica/
#                               .../rfMRI_25.dr  
#                               .../rfMRI_100.dr  
#                               .../filtered_func_data_clean.nii.gz
#                           .../tfMRI.nii.gz
#                           .../rfMRI.feat/
#                               .../filtered_func_data_clean.nii.gz
#                               .../thresh_zfstat1.nii.gz
#                               .../thresh_zfstat2.nii.gz
#                               .../...
#                           .../parcellations/
#                               .../aparc_seq
#                                   .../ts_raw.txt
#                                   .../ts_sc2345.txt
#                               .../500_aparc_seq
#                               .../HCP.fsaverage
#                               .../sjh
```

## Structural imaging
Within the **anat** directory there is a T1 folder with the raw T1 file (*T1_brain.nii.gz*) and two subdirectories containing the FSL [FAST](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FAST) and [FIRST](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FIRST) output for automated segmentations. There is also a T2 directory containing the T2 FLAIR imaging, including any automated lesion masking that might have taken place. Both directories also contain the **_unbiased_brain.nii.gz_** files which are bias field corrected. For a majority of scans UKB provides QC metrics.

### Freesurfer reconstruction
Freesurfer reconstructions have currently been completed succesfully for +/- 39000 datasets using the combined T1 and T2 HCP freesurfer pipeline, see [here](https://www.ncbi.nlm.nih.gov/pubmed/23668970) for more information. They can be found in **~/anat/surfaces/**. Euler indices have been computed as a proxy measure for the quality of the freesurfer reconstruction. For more information on this index see the NeuroImage article on it [here](https://www.ncbi.nlm.nih.gov/pubmed/29278774). Reconstructions include the brainstem [substructure parcellations](http://www.nmr.mgh.harvard.edu/~iglesias/pdf/Neuroimage_2015_brainstem.pdf).   

Pipeline development, analyses, quality control and parcellations of these freesurfer reconstructions were done by Rafael Romero-Garica (rr480), Lisa Ronan (lr344) and Richard A.I. Bethlehem (rb643). When you make use of the freesurfer or parcellated data, please include these people accordingly on any manuscript. Some basic quality control can be found [here](/BasicQC.md/).

### Structural Parcellation
Freesurfer reconstructions have been parcellated using the *desikan killiany atlas*, our in-house *308 parcellation*, the *glasser parcellation*, the *scheaffer200* and *schaeffer400* parcellations and some more fine-grained parcellations (suggestions on which to include in future updates are welcome). All stats files for each respective parcellation can be found in the freesurfer **~/anat/surfaces/{subID}/stats** subdirectory.

## Functional imaging
Within the **func** directory there is a subdirectory for fMRI that contains the resting-state functional imaging data. The *rfMRI* file is the raw EPI data and there are 3 ICA subdirectories; *rfMRI_25.dr* and *rfMRI_100.dr* contain the first stage output from the FSL [Dual-Regression ICA](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/DualRegression) analysis procedure for model with 25 and 100 components respectively (note: it only contains the first stage time-series for each component), the *rfMRI.ica* contains the output files for FSL [FIX ICA](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FIX) denoising, including the *filtered_func_data_clean.nii.gz* file that is the denoised EPI file which can be used in subsequent analyses. For a majority of scans UKB provides QC metrics. See below and overview of the most relevant ones for functional imaging.

### Functional Parcellation
Within **../func/subID/parcellation/** directory there are multiple available parcellations of the FSL-FIX pre-processed time-series (aparc, 308, HCP [360 regions] and SJH [1012 regions]). See the following references respectively: for 308 [here](https://www.ncbi.nlm.nih.gov/pubmed/29274746), for HCP [here](https://www.ncbi.nlm.nih.gov/pubmed/27437579) and for SJH [here](https://www.ncbi.nlm.nih.gov/pubmed/28899007).
Each subdirectory contains the extracted time-series for that parcellation called **ts_raw.txt** and a wavelet filter version called **ts_sc2345.txt** that only includes scales 2-5 (corresponding to a bandwidth of 0.18-0.011Hz). For the wavelet filtered time-series a correlation matrix is also provided **Connectivity_sc2345.txt**. Parcellations were created in subject space by linearly coregistering the subject-space structural freesurfer pre-processed data to the functional denoised time-series that were also in subject space.

## Diffusion weighted imaging
As of February 2020 diffusion weighted data has been made available for approximately 38k subjects. Details of available files and pre-processing pipelines can be found in the UK Biobank whitepaper [here](http://biobank.ctsu.ox.ac.uk/crystal/crystal/docs/brain_mri.pdf). The diffusion directory also contains parcellated files for FA and MD for the same parcellation templates as mentioned above. In addition to the UKB provided diffusion output NODDI reconstructions have been run on all subjects with available data using the [AMICO](https://www.sciencedirect.com/science/article/pii/S1053811914008519#f0010) pipeline found here: https://github.com/daducci/AMICO

### Diffusion Parcellation
For all DWI output and all above mentioned parcellations scheme extracted parcelation values van be found in the parcellation subdirectories.

## Genetics
As of October 2018 polygenic risk have been created for a number of different conditions see the full table [here](https://docs.google.com/spreadsheets/d/1xG4QyBGUXH2NJWeZeiYMgWEA1wrmqDpSQxOK38FNwCs/edit#gid=0). These scores are available upon request by contacting Varun Warrier (vw260@medschl.cam.ac.uk). Please keep in mind the notes outlined in [this](https://docs.google.com/document/d/1Nht_ZT1FA05Uh9Zeh1C-SN7SdXAy_dQ_2Oe6JX2fbN0/edit) document. Code used to generate these scores can be found on: https://github.com/vwarrier/PGSinUKB

# Planned
The following datatypes are available within the present application, but have currently not been downloaded and/or pre-processed yet:  
* follow-up imaging data

# Ongoing projects
A full list of ongoing projects linked to the main application can be found [here](/Projects.md).

# Publications
A full list of published papers linked to the main application can be found [here](/Publications.md).

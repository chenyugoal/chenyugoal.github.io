---
layout: page
title:  Characterizing patterns of DTI variance in aging brains
---

> Diffusion tensor imaging (DTI) measurements of brain microstructure are known to be associated with age. But what about the uncertainty of these measurements? Does it increase or decrease with age? This study explores such relationships and emphasizes the importance of considering heteroscedasticity in analyses.

<figure style="text-align: center;">
  <img src="\research_projects\img\2023_DTI_variance\EveType1_1600px_lossless.gif" alt="Spinning brain gif" style="width:100%; max-width:1950px; height:auto;"/>
  <figcaption>The correlation coefficients of motion (left) and age (right) for fractional anisotropy (FA) across brain regions are shown. Blue indicates a positive correlation; red indicates a negative correlation; and transparent indicates an insignificant correlation in that region.</figcaption>
</figure>


## Purpose

As large analyses merge data across sites, a deeper understanding of variance in statistical assessment across the sources of data becomes critical for valid analyses. Diffusion tensor imaging (DTI) exhibits spatially varying and correlated noise, so care must be taken with distributional assumptions. Here, we characterize the role of physiology, subject compliance, and the interaction of the subject with the scanner in the understanding of DTI variability, as modeled in the spatial variance of derived metrics in homogeneous regions.

<figure style="text-align: center;">
  <img src="\research_projects\img\2023_DTI_variance\DTI_variance_idea_figure.png" alt="Applying the whitening matrix to the standard linear regression equation reduces the number of false positives (FP) and false negatives (FN) under heteroskedasticity." style="width:100%; max-width:1950px; height:auto;"/>
  <figcaption>Why knowing variance matters— an example in linear regression: Simulation shows that applying the whitening matrix (with variance information) to the standard linear regression equation reduces the number of false positives (FP) and false negatives (FN) under heteroskedasticity. In the top row, the population truth has zero slope. In data sampled from the synthetic population data, ordinary least square (OLS) regression using the standard equation generates FP, while the solution with whitening, W, does not falsely reject the null hypothesis (the horizontal line). After 10,000 experiments, the FP frequency is lower with whitening, centering at 5 per 100. In the second row, the population truth has a positive slope. In data sampled from the synthetic population data, OLS regression using the standard equation generates FN, while the solution with whitening, W, does not. After 10,000 experiments, the FN frequency with whitening is half that of the one without whitening.</figcaption>
</figure>


## Approach

We analyze DTI data from 1035 subjects in the Baltimore Longitudinal Study of Aging, with ages ranging from 22.4 to 103 years old. For each subject, up to 12 longitudinal sessions were conducted. We assess the variance of DTI scalars within regions of interest (ROIs) defined by four segmentation methods and investigate the relationships between the variance and covariates, including baseline age, time from the baseline (referred to as "interval"), motion, sex, and whether it is the first scan or the second scan in the session.

<figure style="text-align: center;">
  <img src="\research_projects\img\2023_DTI_variance\DTI_variance_preprocessing.png" alt="Extracting ROI-based DTI variance." style="width:100%; max-width:1950px; height:auto;"/>
  <figcaption>Brain segmentation labels are obtained using the SLANT segmentation of the target subject's T1w image and using three types of manual parcellations provided by the Eve atlas. To generate transformation matrices for transferring these labels to DTI scalar images, intra- and inter-modality registrations are performed. Standard deviations of DTI scalars within each ROI are computed.</figcaption>
</figure>


## Results

Covariate effects are heterogeneous and bilaterally symmetric across ROIs. Inter-session interval is positively related (p ≪ 0.001) to FA variance in the cuneus and occipital gyrus, but negatively (p ≪ 0.001) in the caudate nucleus. Males show significantly (p ≪ 0.001) higher FA variance in the right putamen, thalamus, body of the corpus callosum, and cingulate gyrus. In 62 out of 176 ROIs defined by the Eve type-1 atlas, an increase in motion is associated (p < 0.05) with a decrease in FA variance. Head motion increases during the rescan of DTI (Δμ = 0.045 mm per volume).

<figure style="text-align: center;">
  <img src="\research_projects\img\2023_DTI_variance\DTI_variance_quantitative_3d_brains.png" alt="3D visualization of the effects of motion and interval on FA variance across ROIs." style="width:100%; max-width:1950px; height:auto;"/>
  <figcaption>Despite the different definitions and delineations of ROIs between Eve type-1 and SLANT segmentations, results based on the two segmentation methods are largely similar (comparable regions are colored similarly) and both show that the effects of motion and interval on FA variance vary across ROIs.</figcaption>
</figure>


## Conclusions

The effects of each covariate on DTI variance and their relationships across ROIs are complex. Ultimately, we encourage researchers to include estimates of variance when sharing data and consider models of heteroscedasticity in analysis. This work provides a foundation for study planning to account for regional variations in metric variance.


## Publications

1. **Chenyu Gao**, Qi Yang, Michael E Kim, Nazirah Mohd Khairi, Leon Y Cai, Nancy R Newlin, Praitayini Kanakaraj, Lucas W Remedios, Aravind R Krishnan, Xin Yu, Tianyuan Yao, Panpan Zhang, Kurt G Schilling, Daniel Moyer, Derek B Archer, Susan M Resnick, Bennett A Landman, for the Alzheimer’s Disease Neuroimaging Initiative, the BIOCARD Study team. **"Characterizing patterns of diffusion tensor imaging variance in aging brains"**. Journal of Medical Imaging. 2024. [DOI](https://doi.org/10.1117/1.JMI.11.4.044007)

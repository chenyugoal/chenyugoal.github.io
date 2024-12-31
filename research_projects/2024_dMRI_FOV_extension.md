---
layout: page
title:  FOV extension for brain diffusion MRI via deep generative models
---

> Not all brain diffusion MRI scans capture the entire brain. For scans with an incomplete field of view (FOV), analyses of whole-brain tissue microstructure and connectivity can be severely limited. Instead of discarding such data, can we leverage deep generative models to extend the FOV and recover the missing information? Our approach aims to repair incomplete scans, enabling more comprehensive analyses and preserving valuable data. (Main contributor: [Zhiyuan Li](https://scholar.google.com/citations?hl=en&user=T0yPXRwAAAAJ&view_op=list_works&sortby=pubdate))

<figure style="text-align: center;">
  <img src="\research_projects\img\2024_dMRI_FOV_extension\dMRI_FOV_extension.png" alt="dMRI FOV extension idea" style="width:80%; max-width:2074px; height:auto;"/>
  <figcaption>An incomplete FOV not only makes it impossible to analyze the missing regions but also impacts the tractography performed in the acquired regions (panel (a)), e.g., resulting in missing streamlines of various tracts compared with the reference (panel (c)). Although existing methods can partially impute the missing regions, they struggle with imputing slices near the top edge of the brain, which affects the tractography in those regions (panel (b)).</figcaption>
</figure>


## Purpose

In brain diffusion magnetic resonance imaging (dMRI), the volumetric and bundle analyses of whole-brain tissue microstructure and connectivity can be severely impeded by an incomplete field of view (FOV). We aim to develop a method for imputing the missing slices directly from existing dMRI scans with an incomplete FOV. We hypothesize that the imputed image with a complete FOV can improve whole-brain tractography for corrupted data with an incomplete FOV. Therefore, our approach provides a desirable alternative to discarding the valuable brain dMRI data, enabling subsequent tractography analyses that would otherwise be challenging or unattainable with corrupted data.

## Approach

We propose a framework based on a deep generative model that estimates the absent brain regions in dMRI scans with an incomplete FOV. The model is capable of learning both the diffusion characteristics in diffusion-weighted images (DWIs) and the anatomical features evident in the corresponding structural images for efficiently imputing missing slices of DWIs in the incomplete part of the FOV.

## Results
For evaluating the imputed slices, on the Wisconsin Registry for Alzheimer's Prevention (WRAP) dataset, the proposed framework achieved PSNR_b0 = 22.397, SSIM_b0 = 0.905, PSNR_b1300 = 22.479, and SSIM_b1300 = 0.893; on the National Alzheimer’s Coordinating Center (NACC) dataset, it achieved PSNR_b0 = 21.304, SSIM_b0 = 0.892, PSNR_b1300 = 21.599, and SSIM_b1300 = 0.877. The proposed framework improved the tractography accuracy, as demonstrated by an increased average Dice score for 72 tracts (p < 0.001) on both the WRAP and NACC datasets.

## Conclusions
Results suggest that the proposed framework achieved sufficient imputation performance in brain dMRI data with an incomplete FOV for improving whole-brain tractography, thereby repairing the corrupted data. Our approach achieved more accurate whole-brain tractography results with an extended and complete FOV and reduced the uncertainty when analyzing bundles associated with Alzheimer's disease.


## Publications
1. ***Preliminary Work:*** Chenyu Gao, Shunxing Bao, Michael E Kim, Nancy R Newlin, Praitayini Kanakaraj, Tianyuan Yao, Gaurav Rudravaram, Yuankai Huo, Daniel Moyer, Kurt Schilling, Walter A Kukull, Arthur W Toga, Derek B Archer, Timothy J Hohman, Bennett A Landman, Zhiyuan Li. **"Field-of-view extension for brain diffusion MRI via deep generative models"**. Journal of Medical Imaging. 2024. [DOI](https://doi.org/10.1117/1.JMI.11.4.044008)
2. ***Follow-Up Work:*** Zhiyuan Li, Tianyuan Yao, Praitayini Kanakaraj, Chenyu Gao, Shunxing Bao, Lianrui Zuo, Michael E Kim, Nancy R Newlin, Gaurav Rudravaram, Nazirah M Khairi, Yuankai Huo, Kurt G Schilling, Walter A Kukull, Arthur W Toga, Derek B Archer, Timothy J Hohman, Bennett A Landman. **"Multi-Modality Conditioned Variational U-Net for Field-of-View Extension in Brain Diffusion MRI"**. 2024. [arXiv](https://arxiv.org/abs/2409.13846)
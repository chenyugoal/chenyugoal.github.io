---
layout: page
title:  Effects of defacing whole-head MRI on brain segmentation
---

> What are the costs of privacy protection through defacing?

<figure style="text-align: center;">
  <img src="\research_projects\img\2022_Defacing\Defacing_3D_Rendering_All_Methods.png" alt="3D rendering of defacing methods" style="width:100%; max-width:1950px; height:auto;"/>
  <figcaption>A sagittal slice of an MRI is displayed over the reconstruction of the whole head MRI.</figcaption>
</figure>


## Purpose

Recent advances in magnetic resonance (MR) scanner quality and the rapidly improving nature of facial recognition software have necessitated the introduction of MR defacing algorithms to protect patient privacy. As a result, there are a number of MR defacing algorithms available to the neuroimaging community, with several appearing in just the last 5 years. While some qualities of these defacing algorithms, such as patient identifiability, have been explored in the previous works, the potential impact of defacing on neuroimage processing has yet to be explored.


## Approach

We qualitatively evaluate eight MR defacing algorithms on 179 subjects from the OASIS-3 cohort and 21 subjects from the Kirby-21 dataset. We also evaluate the effects of defacing on two neuroimaging pipelines—SLANT and FreeSurfer—by comparing the segmentation consistency between the original and defaced images.


## Results

Defacing can alter brain segmentation and even lead to catastrophic failures, which are more frequent with some algorithms, such as Quickshear, MRI_Deface, and FSL_deface. Compared to FreeSurfer, SLANT is less affected by defacing. On outputs that pass the quality check, the effects of defacing are less pronounced than those of rescanning, as measured by the Dice similarity coefficient.


## Conclusions

The effects of defacing are noticeable and should not be disregarded. Extra attention, in particular, should be paid to the possibility of catastrophic failures. It is crucial to adopt a robust defacing algorithm and perform a thorough quality check before releasing defaced datasets. To improve the reliability of analysis in scenarios involving defaced MRIs, it is encouraged to include multiple brain segmentation pipelines.


## Publications

1. Chenyu Gao, Linghao Jin, Jerry L Prince, Aaron Carass. **"Effects of defacing whole head MRI on neuroanalysis"**. Medical Imaging 2022: Image Processing. International Society for Optics and Photonics (SPIE). 2022. [DOI](https://doi.org/10.1117/12.2613175)
2. Chenyu Gao, Bennett A. Landman, Jerry L. Prince, Aaron Carass. **"Reproducibility evaluation of the effects of MRI defacing on brain segmentation"**. Journal of Medical Imaging. 2023. [DOI](https://doi.org/10.1117/1.JMI.10.6.064001)

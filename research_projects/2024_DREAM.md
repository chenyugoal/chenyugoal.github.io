---
layout: page
title:  "Pitfalls of defacing whole-head MRI: re-identification risk with diffusion models and compromised research potential"
---

> Defacing is often applied to head magnetic resonance image (MRI) datasets prior to public release to address privacy concerns. Our findings indicate that (1) diffusion probabilistic models can recover faces from defaced MRIs, thereby questioning defacing as a privacy protection measure, and (2) defacing alters facial voxels which contain valuable anatomical information for secondary analyses, such as skeletal muscle radiodensity prediction. [[arXiv](https://arxiv.org/abs/2501.18834)]


<figure style="text-align: center;">
  <img src="\research_projects\img\2024_DREAM\DREAM_Problems.png" alt="Pitfalls of defacing" style="width:80%; max-width:1950px; height:auto;"/>
  <figcaption>There are pitfalls of defacing, a technique used to alter facial voxels in whole-head MRIs to protect privacy. First, with deep generative models such as diffusion probabilistic models, it is possible to synthesize MRIs with realistic faces, which closely resemble the original faces, from defaced MRIs. This capability poses a re-identification risk, thus questioning the efficacy of defacing in protecting privacy. Second, facial and other non-brain voxels in whole-head MRIs contain valuable anatomical information. For instance, this information could be used to study correlations between head and body measurements using paired head MRI and body CT data. The alteration of these voxels results in information loss, thereby compromising such research potentials. The experiments in this paper are designed to showcase these two pitfalls.</figcaption>
</figure>


## Key Results
#### 1. Diffusion probabilistic models can recover faces from defaced MRIs

<figure style="text-align: center;">
  <img src="\research_projects\img\2024_DREAM\DREAM_3D_Rendering_Faces.png" alt="3D Rendering of Faces" style="width:100%; max-width:1950px; height:auto;"/>
  <figcaption>For an example subject, 3D renderings of the faces in the original image, image defaced by MRI_Deface, image refaced from the defaced image by our diffusion probabilistic models, and image processed with mri_reface (which replaces the original face with a population average face) are presented in each row. The mean absolute surface distance is computed between the original face and the face in each image type. A smaller distance corresponds to a higher similarity to the original face.</figcaption>
</figure>


#### 2. Facial voxels removed by defacing contain valuable anatomical information

<figure style="text-align: center;">
  <img src="\research_projects\img\2024_DREAM\DREAM_Prediction_Correlations.png" alt="Skeletal Muscle Radiodensity Prediction Correlations" style="width:75%; max-width:1950px; height:auto;"/>
  <figcaption>The correlation between predicted residuals of abdomen, thigh, and shin muscle radiodensity (measured from segmented ROI in CT data, in Hounsfield units, with age and sex regressed out using linear models) and ground truth values is stronger using original images compared to defaced or skull-stripped images. The image types are arranged such that those with more facial voxels removed are placed on the right (e.g., skull-stripping), while those with fewer facial voxels removed are placed on the left (e.g., original). As more voxels are removed, the correlation between head and body becomes weaker and more difficult to capture. For instance, the correlations between predicted abdomen muscle radiodensity from FSL_deface, MRI_Deface, Pydeface, and skull-stripped images and the ground truth values are not statistically significant, as indicated by 95% confidence intervals (CI) overlapping with 0. For shin muscle, the head-body correlation is statistically significant only when using original images. Bootstrapping (n=1000) is used to estimate the mean and 95% confidence intervals of the Spearman’s rank correlation coefficients. Statistical significance is indicated by “****” for p-value ≤ 10-4, based on the Wilcoxon signed-rank test.</figcaption>
</figure>

## Please refer to the following paper for more details:
- Chenyu Gao, Kaiwen Xu, Michael E. Kim, Lianrui Zuo, Zhiyuan Li, Derek B. Archer, Timothy J. Hohman, Ann Zenobia Moore, Luigi Ferrucci, Lori L. Beason-Held, Susan M. Resnick, Christos Davatzikos, Jerry L. Prince, Bennett A. Landman. **"Pitfalls of defacing whole-head MRI: re-identification risk with diffusion models and compromised research potential"**. [[arXiv](https://arxiv.org/abs/2501.18834)]

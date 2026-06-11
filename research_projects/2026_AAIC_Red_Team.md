---
layout: page
title:  "Red Teaming mri_reface: Assessing Reversibility via Diffusion-Based Facial Reconstruction Attacks"
---

> Can *mri_reface* survive our red-team privacy attack?

<img src="\research_projects\img\2026_AAIC_Red_Team\poster.png" alt="AAIC poster" style="width:100%; max-width:1950px; height:auto;"/>

## Background
Open sharing of neuroimaging data is critical for accelerating Alzheimer’s disease research; however, facial structure inherent in head MRI poses re-identification risk. While traditional defacing removes facial voxels (often compromising downstream processing, see [this blog](2022_DEFACE.md)), mri_reface replaces the face with a realistic, synthetic alternative to preserve data utility. With the rise of generative AI—specifically, diffusion models for image inpainting and restoration—there is concern that “defacing” could be reversed. (see [this blog](2024_DREAM.md)) This study conducts a red-team evaluation to assess mri_reface against state-of-the-art reconstruction attacks.

<figure style="text-align: center;">
  <img src="\research_projects\img\2026_AAIC_Red_Team\Fig_1_idea.png" alt="Overview of the problem" style="width:80%; max-width:1950px; height:auto;"/>
</figure>

## Methods
We used 200 T1-weighted images to train and validate a simulated adversarial model, and an independent set of 469 as the target dataset. We processed the target images with mri_reface 0.3.5 and attempted to reconstruct the original faces using three increasing levels of attack sophistication. Approach 1 applied a secondary defacing tool (FSL_deface) to the mri_reface output to remove broad facial voxels, followed by a pre-trained diffusion model (see [this blog](2024_DREAM.md)) for reversing FSL_deface. Approach 2 attempted to reverse-engineer the mri_reface mask by running the tool a second time and exploiting processing variability to segment and remove the synthetic voxels, followed by Approach 1’s pre-trained diffusion model. Approach 3 used Approach 2’s mask-approximation strategy but employed a diffusion model fine-tuned on the training data to reconstruct the removed regions.

## Results
In Approach 1, the residual synthetic features confounded the diffusion model, resulting in realistic faces that did not resemble the original subjects. In Approach 2, the pre-trained model failed to generalize to the aggressive cropping required by the mask removal. Approach 3 achieved the highest visual quality; however, quantitative analysis revealed that the reconstructed faces were, in terms of surface distance, no closer to the ground truth than a registered population average.

<figure style="text-align: center;">
  <img src="\research_projects\img\2026_AAIC_Red_Team\Fig_2_quantitative.png" alt="Quantitative Results" style="width:80%; max-width:1950px; height:auto;"/>
</figure>

## Conclusions
mri_reface exhibits remarkable robustness against diffusion-based reconstruction attacks, outperforming other methods we tested previously. Our findings suggest that mri_reface’s replacing facial features with seamless synthetic data provides superior protection compared to naive voxel removal. The difficulty of precisely segmenting the synthetic mask prevents attackers from easily isolating the regions to be reconstructed (which are also larger and more comprehensive), effectively preserving privacy while maintaining data utility.

## Related Publications
1. Chenyu Gao, Linghao Jin, Jerry L Prince, Aaron Carass. **"Effects of defacing whole head MRI on neuroanalysis"**. *Medical Imaging 2022: Image Processing*. International Society for Optics and Photonics (SPIE). 2022. [DOI](https://doi.org/10.1117/12.2613175)
2. Chenyu Gao, Bennett A. Landman, Jerry L. Prince, Aaron Carass. **"Reproducibility evaluation of the effects of MRI defacing on brain segmentation"**. *Journal of Medical Imaging*. 2023. [DOI](https://doi.org/10.1117/1.JMI.10.6.064001)
3. Chenyu Gao, Kaiwen Xu, Michael E. Kim, Lianrui Zuo, Zhiyuan Li, Derek B. Archer, Timothy J. Hohman, Ann Zenobia Moore, Luigi Ferrucci, Lori L. Beason-Held, Susan M. Resnick, Christos Davatzikos, Jerry L. Prince, Bennett A. Landman. **"Pitfalls of defacing whole-head MRI: re-identification risk with diffusion models and compromised research potential"**. *Computers in Biology and Medicine* 197 (2025): 111112. [[DOI](https://doi.org/10.1016/j.compbiomed.2025.111112)][[arXiv](https://arxiv.org/abs/2501.18834)]
4. Chenyu Gao, Michael E. Kim, Yihao Liu, Kaiwen Xu, Trent M. Schwartz, Lianrui Zuo, Zhiyuan Li, Derek B. Archer, Timothy J. Hohman, Ann Zenobia Moore, Luigi Ferrucci, Lori L. Beason-Held, Susan M. Resnick, Christos Davatzikos, Jerry L. Prince, Christopher G. Schwarz, Bennett A. Landman. **"Red Teaming mri_reface: Assessing Reversibility via Diffusion-Based Facial Reconstruction Attacks"**. AAIC 2026 (poster).
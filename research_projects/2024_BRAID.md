---
layout: page
title:  "BRAID: Brain Age Identification from Diffusion MRI"
---

> Traditional brain age estimation often relies on macro-structural features, such as the size and shape of brain regions. In this study, we take a novel approach by intentionally discarding such information through deformable registration, directing the model's attention to micro-structural features within diffusion MRI. These subtle, textural patterns are known to change earlier than macro-structural features in neurodegenerative diseases like Alzheimer's, offering the potential for earlier detection and intervention. [[GitHub](https://github.com/MASILab/BRAID)] [[arXiv](https://arxiv.org/abs/2410.22454)]


<figure style="text-align: center;">
  <img src="\research_projects\img\2024_BRAID\BRAID_figure_idea.png" alt="BRAID idea figure" style="width:80%; max-width:1950px; height:auto;"/>
  <figcaption>Brain age estimation frameworks have proven effective for using affinely aligned brain images to identify common patterns of aging, with deviations from these patterns likely indicating presence of abnormal neuropathologic processes. A common theme of existing brain age estimation methods has been using T1w MRI, denoted as “GM age” in the first row. Among them, there have been many innovations in network design, such as DeepBrainNet (DBN) (Bashyam et al., 2020) and the 3D convolutional neural network of TSAN (Cheng et al., 2021). T1w MRI lacks detail in white matter (WM). Here, we take the two most commonly used modalities for characterizing WM microstructure, fractional anisotropy (FA), and mean diffusivity (MD), and we evaluate brain age estimation in two contexts. First, we examine the direct substitution of FA and MD for T1w image, which we denote as “WM age affine” in the second row. A substantial amount of macrostructural differences is still present in WM age affine, notably ventricle enlargement. To isolate the microstructural changes, we apply non-rigid (deformable) registration into template space to mitigate the macrostructural changes and produce the “WM age nonrigid” in the third row.</figcaption>
</figure>


## The Research Topic

Brain age estimation is an important and popular research topic. As of the time this page was written, there were approximately **2,350,000 results** on Google Scholar for the query *"brain age MRI"*. Numerous brain age estimation models already exist. Before introducing ours, I'd like to discuss what **an "ideal" brain age estimation model** should look like.


## Specificity & Sensitivity

For machine learning models, especially those used in clinical applications, **specificity** and **sensitivity** are two critical aspects.

In the context of brain age estimation:

- **Specificity** refers to the model's ability to **accurately estimate the chronological age** of individuals who are neither experiencing nor on a trajectory to develop neurodegenerative diseases or cognitive decline
- **Sensitivity**, on the other hand, refers to the model's ability to **detect deviations**[^1] from the normal aging trajectory for individuals who are either experiencing or on a trajectory to develop **neurodegenerative diseases** or **cognitive decline** before clinical diagnosis.

Considerable efforts have been made to enhance the **specificity** of brain age estimation models, as reflected in studies reporting lower and lower **mean absolute errors (MAEs)**. Comparatively, fewer efforts have been directed toward improving the **sensitivity** of these models.

However, **sensitivity** is just as important as specificity—perhaps even more important from my perspective. After all, we want the model to **alert** us if the brain is developing a disease, rather than acting as a perfect chronological age predictor—which has limited clinical value (we can simply ask how old a person is in most cases, right?).

[^1]: Simply, for individuals with an “unhealthy” brain, the brain age should appear older than the chronological age.


## Our Goal: An Earlier Biomarker

We want to push sensitivity further!

With that goal in mind, we refined our objective: to provide **an earlier biomarker** for neurodegenerative disease prediction. The definition of "earlier" is illustrated in the sketch below, where the blue curve represents our target. Ideally, the estimated brain age should deviate from the chronological age before disease onset—earlier than conventional brain age models.


<figure style="text-align: center;">
  <img src="\research_projects\img\2024_BRAID\BRAID_goal_sketch.png" alt="BRAID goal sketch" style="width:50%; max-width:1306px; height:auto;"/>
  <figcaption>BRAID's goal (simplified).</figcaption>
</figure>


## Diffusion MRI, Micro- and Macro-Structural Features

Diffusion MRI (dMRI) presents an opportunity to build an earlier biomarker for neurodegenerative disease prediction because it captures subtle microstructural changes that precede more perceptible macrostructural changes. Examples of dMRI accompanied by T1-weighted MRI are shown below.

<figure style="text-align: center;">
  <img src="\research_projects\img\2024_BRAID\BRAID_example_T1w_dMRI.png" alt="Examples of T1w and diffusion MRI" style="width:100%; max-width:2892px; height:auto;"/>
  <figcaption>Examples of T1w and diffusion MRI.</figcaption>
</figure>

We are interested in the **microstructural** features (i.e., the "**texture**") in dMRI. However, **macrostructural** features (i.e., the "**shape**") are also present in dMRI. This confounding factor reminds me of an ICLR paper:
> Geirhos, Robert, et al. "ImageNet-trained CNNs are biased towards texture; increasing shape bias improves accuracy and robustness." ICLR (2019).

In that paper, the authors sought to make CNN models focus on shape instead of texture for image classification. Interestingly, this is the opposite of what we aim to achieve.

<figure style="text-align: center;">
  <img src="\research_projects\img\2024_BRAID\Geirhos_et_al_ICLR_key_figures.png" alt="Key figures of the ICLR paper by Geirhos et al." style="width:70%; max-width:2809px; height:auto;"/>
  <figcaption>Idea figures from the ICLR paper by Geirhos et al.</figcaption>
</figure>


## Mitigating the Macrostructural Features

To mitigate macrostructural information, we applied non-rigid (deformable) transformations.

We warped all brains to align with a template brain, ensuring that all brains appear similar in terms of shape and size. By deliberately discarding macrostructural information, we "force" the model to focus more on the microstructural features.

<figure style="text-align: center;">
  <img src="\research_projects\img\2024_BRAID\BRAID_warp_brains.png" alt="Brains before and after the nonrigid transformations." style="width:100%; max-width:1950px; height:auto;"/>
  <figcaption>The macrostructural variations are present in the affine-aligned fractional anisotropy (FA) images, while minimized in the nonrigid-aligned images. Contours of regions are provided to assist in the visual inspection of brain region shapes. Yellow arrows indicate the thalamus, which appears to shrink with age in the first row (affine-aligned) but remains consistent in shape and size in the second row (nonrigid-aligned).</figcaption>
</figure>


## Finally, We Made It!

Our approach, **BRAID**, delivers an earlier biomarker, which we name "WM age nonrigid". In short, this biomarker can predict **mild cognitive impairment** (MCI)—a condition associated with a higher risk of developing **Alzheimer’s disease** (AD) or other forms of dementia—earlier than other brain age models. One of our findings is shown below. 

<figure style="text-align: center;">
  <img src="\research_projects\img\2024_BRAID\BRAID_matched_cohort_diagnosis.png" alt="Bland–Altman plot of WM age vs GM age across matched cohorts." style="width:80%; max-width:1950px; height:auto;"/>
  <figcaption>Data points from four diagnostic groups (CN: cognitively normal; CN*: cognitively normal at present but diagnosed with MCI in 2.4 ± 1.2 years; MCI: mild cognitive impairment; AD: Alzheimer's disease) were matched for age, sex, time to last CN, and time to first MCI (for matching CN and CN* data points). Among CN* participants, our WM age nonrigid was significantly higher than GM age. Among AD participants, our WM age nonrigid was significantly lower than GM age. In CN and MCI participants, the difference was not significant. These findings may suggest that WM age nonrigid is sensitive to the early stages of cognitive decline, while GM age captures more perceptible anatomical changes in the later stages of cognitive decline.</figcaption>
</figure>

## Publications
1. Chenyu Gao, Michael E. Kim, Karthik Ramadass, Praitayini Kanakaraj, Aravind R. Krishnan, Adam M. Saunders, Nancy R. Newlin, Ho Hin Lee, Qi Yang, Warren D. Taylor, Brian D. Boyd, Lori L. Beason-Held, Susan M. Resnick, Lisa L. Barnes, David A. Bennett, Katherine D. Van Schaik, Derek B. Archer, Timothy J. Hohman, Angela L. Jefferson, Ivana Išgum, Daniel Moyer, Yuankai Huo, Kurt G. Schilling, Lianrui Zuo, Shunxing Bao, Nazirah Mohd Khairi, Zhiyuan Li, Christos Davatzikos, Bennett A. Landman for the Alzheimer’s Disease Neuroimaging Initiative and the BIOCARD Study team. **"Brain age identification from diffusion MRI synergistically predicts neurodegenerative disease"**. [[arXiv](https://arxiv.org/abs/2410.22454)]
2. Chenyu Gao, Michael E Kim, Ho Hin Lee, Qi Yang, Nazirah Mohd Khairi, Praitayini Kanakaraj, Nancy R Newlin, Derek B Archer, Angela L Jefferson, Warren D Taylor, Brian D Boyd, Lori L Beason-Held, Susan M Resnick, Yuankai Huo, Katherine D Van Schaik, Kurt G Schilling, Daniel Moyer, Ivana Išgum, Bennett A Landman. **"Predicting age from white matter diffusivity with residual learning"**. Medical Imaging 2024: Image Processing. International Society for Optics and Photonics (SPIE). 2024. [DOI](https://doi.org/10.1117/12.3006525)

## Intellectual property (IP)

*A provisional patent has been filed. We welcome inquiries regarding investment and collaboration opportunities to advance and commercialize this technology.*

1. Chenyu Gao, Bennett A. Landman, Michael E. Kim. 2024. **System and Method of Brain Age Identification for Predicting Neuro-Degenerative Disease**. U.S. Patent 63/701,861, filed Oct 1, 2024. Provisional patent.

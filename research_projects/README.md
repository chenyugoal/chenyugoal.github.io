---
layout: page
title:  Research Projects
---

## 2024
[Pitfalls of defacing whole-head MRI: re-identification risk with diffusion models and compromised research potential]{:.heading.flip-title}

Defacing is often applied to head magnetic resonance image (MRI) datasets prior to public release to address privacy concerns. Our findings indicate that (1) diffusion probabilistic models can recover faces from defaced MRIs, thereby questioning defacing as a privacy protection measure, and (2) defacing alters facial voxels which contain valuable anatomical information for secondary analyses, such as skeletal muscle radiodensity prediction. [[arXiv](https://arxiv.org/abs/2501.18834)]
{:.faded}

<img src="\research_projects\img\2024_DREAM\DREAM_Problems.png" alt="Pitfalls of defacing" style="width:80%; max-width:1950px; height:auto;"/>


## 2024
[BRAID: Brain Age Identification from Diffusion MRI]{:.heading.flip-title}

Traditional brain age estimation often relies on macro-structural features, such as the size and shape of brain regions. In this study, we take a novel approach by intentionally discarding such information through deformable registration, directing the model's attention to micro-structural features within diffusion MRI. These subtle, textural patterns are known to change earlier than macro-structural features in neurodegenerative diseases like Alzheimer's, offering the potential for earlier detection and intervention. [[GitHub](https://github.com/MASILab/BRAID)] [[arXiv](https://arxiv.org/abs/2410.22454)]
{:.faded}

<img src="\research_projects\img\2024_BRAID\BRAID_figure_idea.png" alt="BRAID idea figure" style="width:80%; max-width:1950px; height:auto;"/>


## 2024
[FOV extension for brain diffusion MRI via deep generative models]{:.heading.flip-title}

Not all brain diffusion MRI scans capture the entire brain. For scans with an incomplete field of view (FOV), analyses of whole-brain tissue microstructure and connectivity can be severely limited. Instead of discarding such data, can we leverage deep generative models to extend the FOV and recover the missing information? Our approach aims to repair incomplete scans, enabling more comprehensive analyses and preserving valuable data. (Main contributor: [Zhiyuan Li](https://scholar.google.com/citations?hl=en&user=T0yPXRwAAAAJ&view_op=list_works&sortby=pubdate))
{:.faded}

<img src="\research_projects\img\2024_dMRI_FOV_extension\dMRI_FOV_extension.png" alt="dMRI FOV extension idea" style="width:80%; max-width:2074px; height:auto;"/>

## 2023
[Characterizing patterns of DTI variance in aging brains]{:.heading.flip-title}

Diffusion tensor imaging (DTI) measurements of brain microstructure are known to be associated with age. But what about the uncertainty of these measurements? Does it increase or decrease with age? This study explores such relationships and emphasizes the importance of considering heteroscedasticity in analyses.
{:.faded}

<img src="\research_projects\img\2023_DTI_variance\EveType1_1600px_lossless.gif" alt="Spinning brain gif" style="width:80%; max-width:512px; height:auto;"/>


## 2022

[Effects of defacing whole-head MRI on brain segmentation]{:.heading.flip-title}

What are the costs of privacy protection through MRI defacing?
{:.faded} 

<img src="\research_projects\img\2022_Defacing\Defacing_3D_Rendering_All_Methods.png" alt="3D rendering of defacing methods" style="width:80%; max-width:1950px; height:auto;"/>


## 2021 
[Shiny APP for Bird Recognition Using Convolutional Neural Network]{:.heading.flip-title}

An easy-to-use [website](https://m250.shinyapps.io/bird_recognition/) for bird image classification. 
Upload an image of bird, 
then it will tell you the top-5 most likely bird species it belongs to.
(Advisor: Prof. [Brian Caffo](https://sites.google.com/view/bcaffo/home))
{:.faded} 

<br/>
<iframe width="560" height="315" src="https://www.youtube.com/embed/_Ax88Q_l0P4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 2021
[Multimodal Brain Tumor Segmentation and Survival Prediction]{:.heading.flip-title}

This is the final project (II) of *Medical Image Analysis*. 
We implemented a 3D Multimodal U-Net with sparse annotation, 
and a Cascaded Anisotropic Convolutional Neural Networks for brain tumor segmentation respectively.
Based on the segmentation result, 
we extract Radiomics features and predict on the survival time of patient using regression tree ensembles.
(Advisor: Prof. [Jerry Prince](http://iacl.jhu.edu/index.php?title=Prince))
{:.faded} 

<br/>
<iframe width="560" height="315" src="https://www.youtube.com/embed/l_EKNv7wyXg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## 2021
[Neural Decoding for Patients with Upper Limb Paralysis]{:.heading.flip-title}

Inspired by the experiment of Elon Musk’s Neuralink, 
where the monkey could play video games with its brain, 
we implemented two algorithms for neural decoding, 
the Long Short-term Memory Networks and the Kalman Filter, 
in our course project of *Neural Implants & Interfaces*.
(Advisor: Prof. [Gene Fridman](https://www.hopkinsmedicine.org/profiles/details/gene-fridman))
{:.faded} 

<br/>
<iframe width="560" height="315" src="https://www.youtube.com/embed/NOyhoJYvcIE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 2020 - 2021
[Progressive Learning: A Potential Algorithm for Lifelong Learning Machines]{:.heading.flip-title}

In biological learning, 
data are used to improve performance simultaneously on the current task, 
as well as previously encountered and as yet unencountered tasks. 
In contrast, classical machine learning starts from a blank slate, 
or tabula rasa, using data only for the single task at hand. 
While typical transfer learning algorithms can improve performance on future tasks, 
their performance on prior tasks degrades upon learning new tasks (called "catastrophic forgetting"). 
Many recent approaches have attempted to maintain performance given new tasks. 
But striving to avoid forgetting sets the goal unnecessarily low: 
the goal of ProgLearn is to improve performance on all tasks (including past and future) with any new data.
(Advisor: Prof. [Joshua Vogelstein](https://jovo.me/))
{:.faded} 

<br/>
<img src="\research_projects\img\2021_NDD\learning_schema_new.png" alt="drawing" width="640"/>

## Undergraduate research (before 2020)

[Bioactive Scaffolds for Bone Tissue Engineering]{:.heading.flip-title}

Bone is well known for its self-healing abilities. However, for large-scale defects, 
bone cannot heal itself completely. In such case, external intervention is needed. 
By implanting bioactive scaffolds into the defect area, 
we provide places for cells to adhere, proliferate and differentiate, 
thus accelerating the process of bone tissue regeneration. 
Below is the schematic illustration of bioactive gelatin cryogels 
with BMP-2 biomimetic peptide and VEGF for synergistically induced osteogenesis. 
The paper has been accepted by *Chinese Chemical Letters*.
(Advisor: Prof. [Jun Wu](https://scholar.google.com/citations?user=adrSJigAAAAJ&hl=en&oi=ao))
{:.faded} 

<br/>
<img src="\research_projects\img\2020_BONE\CCLET-D-21-01349_R2.jpg" alt="drawing" width="480"/>



<!-- Links -->
[Shiny APP for Bird Recognition Using Convolutional Neural Network]: 2021_DS_APP.md
[Multimodal Brain Tumor Segmentation and Survival Prediction]: 2021_MIA_brain_tumor_seg.md
[Neural Decoding for Patients with Upper Limb Paralysis]: 2021_NII_project_decoding.md
[Progressive Learning: A Potential Algorithm for Lifelong Learning Machines]: 2021_NDD_progressive_learning.md
[Bioactive Scaffolds for Bone Tissue Engineering]: 2020_UG_BONE.md
[Effects of defacing whole-head MRI on brain segmentation]: 2022_DEFACE.md
[BRAID: Brain Age Identification from Diffusion MRI]: 2024_BRAID.md
[FOV extension for brain diffusion MRI via deep generative models]: 2024_dMRI_FOV_extension.md
[Characterizing patterns of DTI variance in aging brains]: 2023_DTI_variance.md
[Pitfalls of defacing whole-head MRI: re-identification risk with diffusion models and compromised research potential]: 2024_DREAM.md
---
layout: page
title:  Research Projects
---



# Since 2020

[Effects of Defacing Whole Head MRI on Neuroanalysis]{:.heading.flip-title}

Recent advances in magnetic resonance (MR) scanner quality and 
the rapidly improving nature of facial recognition software 
have necessitated the introduction of MR defacing algorithms to protect patient privacy. 
As a result, there are a number of MR defacing algorithms available to the neuroimaging community, 
with several appearing in just the last five years. 
These various approaches have qualities that have been explored 
with respect to skull stripping masks or identifiability of the patient 
in previous works. However, to our knowledge 
there has been no evaluation of the subsequent impact of these defacing algorithms 
on a neuroimaging pipeline. In this work, we use six MR defacing algorithms 
on 179 subjects from the OASIS-3 cohort and 21 subjects from the Kirby 21 dataset, 
then apply a neuroimaging pipeline to the resultant defaced images. 
We compare the consistency of the output from the pipeline using the defaced images 
with the output of the same pipeline without defacing the MR data. 
(Advisor: Prof. [Jerry Prince](http://iacl.jhu.edu/index.php?title=Prince))
{:.faded} 

<br/>
<img src="\research_projects\img\2022_Defacing\Defacing_3D_Rendering_All_Methods.png" alt="drawing" width="640"/>

[Shiny APP for Bird Recognition Using Convolutional Neural Network]{:.heading.flip-title}

An easy-to-use [website](https://m250.shinyapps.io/bird_recognition/) for bird image classification. 
Upload an image of bird, 
then it will tell you the top-5 most likely bird species it belongs to.
(Advisor: Prof. [Brian Caffo](https://sites.google.com/view/bcaffo/home))
{:.faded} 

<br/>
<iframe width="560" height="315" src="https://www.youtube.com/embed/_Ax88Q_l0P4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

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

# Undergraduate

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

[Shiny APP for Bird Recognition Using Convolutional Neural Network]: 2021_DS_APP.md
[Multimodal Brain Tumor Segmentation and Survival Prediction]: 2021_MIA_brain_tumor_seg.md
[Neural Decoding for Patients with Upper Limb Paralysis]: 2021_NII_project_decoding.md
[Progressive Learning: A Potential Algorithm for Lifelong Learning Machines]: 2021_NDD_progressive_learning.md
[Bioactive Scaffolds for Bone Tissue Engineering]: 2020_UG_BONE.md
[Effects of Defacing Whole Head MRI on Neuroanalysis]: 2022_DEFACE.md
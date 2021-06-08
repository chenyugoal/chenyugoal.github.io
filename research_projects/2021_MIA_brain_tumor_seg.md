---
layout: page
title:  Multimodal Brain Tumor Segmentation and Survival Prediction
---

> Quantitative analysis of brain tumors is critical for clinical decision-making. 
> While manual segmentation is tedious, time-consuming and subjective, 
> this task is at the same time very challenging to solve for automatic segmentation methods. 
> Here, we implement U-Net and Cascaded Anisotropic Convolutional Neural Networks (CACNN) 
> for brain tumor segmentation. 
> On the validation sets, the CACNN gets higher dice coefficients than the U-Net in all subregions of tumor. 
> Based on the segmentation result, 
> we furthermore extract radiomic features to train a regression tree ensemble 
> to predict on the survival time of the patient.

## Methods

### Dataset and Preprocessing

<img src="\research_projects\img\2021_MIA\dataset_preview.png" alt="drawing" width="800"/>

Sample slice from the dataset.
{:.figcaption}

We used a dataset that contains multimodal magnetic resonance imaging (MRI) scans 
from 100 patients for experiments. 
Each patient was scanned with four sequences: 
T1-weighted, T2-weighted, Post-contrast T1-weighted, 
and T2 Fluid Attenuated Inversion Recovery (FLAIR). 
All the images were skull-stripped and re-sampled to 
an isotropic 1 mm<sup>3</sup> resolution, 
and the four sequences of the same patient had been co-registered. 
The ground truth was obtained by manual segmentation results given by experts, 
comprising 4 labels: 
the enhancing tumor (ET), the peritumoral edema (ED), 
the necrotic and non-enhancing tumor core (NCR/NET), and the background. 
For 41 patients of the 100, we had access to their age and survival time, 
which were used in combination with the segmentation results 
to build a regression model for survival prediction.

### Tumor Segmentation
We implemented two convolutional neural networks respectively to segment the brain tumor. 
One is a 3D multimodal U-net inspired by Özgün ÇİÇEK et al., 
and the other is a cascaded anisotropic convolutional neural networks (CACNN) 
proposed by Wang et al. during the BRATS 2017 Challenge.

The 3D U-net (Özgün ÇİÇEK et al.) is based on the original U-net architecture, 
which consists of a contracting encoder part to analyze the whole image, 
and a successive expanding decoder part to produce a full-resolution segmentation. 
The author replaced the corresponding kernels and operations from 2D to 3D, 
thus generalizing its application to volumetric data. 

<img src="\research_projects\img\2021_MIA\u-net.png" alt="drawing" width="800"/>

Schematic of the 3D multimodal U-net.
{:.figcaption}

To accomplish multi-modal fusion, 
i.e., to take the advantages of each modality, 
we modified the input layer of the network 
by stacking the 3D MR images of each patient together 
to a 4D array with a size of 240x240x155x4. 

One challenge of medical image segmentation is the amount of memory needed 
to store and process 3-D volumes. 
Training a network on the full input volume is impractical due to GPU resource constraints. 
Here we solve the problem by training the network on image patches 
with a size of 132x132x132. 
To increase the training set, we performed data augmentation (same for the CACNN) 
by rotation, shifting, flipping, and so on. 
    
The cascaded anisotropic convolutional neural networks (CACNN) (Wang et al.)
segment brain tumor subregions sequentially. 
The highlight of this model is the attempt 
to separate the complex problem of multiple class segmentation 
into three simpler binary segmentation problems, 
and to take advantage of the hierarchical structure of tumor subregions 
to reduce false positives. 
Also, the author proposes to fuse the output of CNNs 
in three orthogonal views for more robust segmentation of brain tumor. 
We replicated this model and finished the training process in Python using PyTorch.

<img src="\research_projects\img\2021_MIA\cacnn.png" alt="drawing" width="800"/>

The triple cascaded framework for brain tumor segmentation.
{:.figcaption}

### Survival Prediction

The survival prediction is very challenging due to the absence of treatment information 
and the small size of the available dataset.
For only 41 patients, the age and the survival information are provided 
in addition to their MR image data.

Our approach to survival prediction is based on [Radiomics](https://github.com/mvallieres/radiomics), 
a package providing MATLAB programming tools for radiomics analysis. 
We computed the texture features and non-texture features for each subregion of tumors 
and for each volume from different modalities. 
After appending the age information and removing repeated non-texture features, 
we extracted a total of 701 features.

These features were then used for training a regression tree ensemble 
for survival prediction. 
We performed Principal Component Analysis (PCA) 
and kept enough components to explain 95% of the variance. 
We used bagging as the ensemble method and searched for the optimized hyperparameters 
that minimize the mean squared error (MSE), using 5-fold cross-validation.


## Presentation

<iframe width="560" height="315" src="https://www.youtube.com/embed/l_EKNv7wyXg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>

Speaker: Angelina Zhu, Chenyu Gao

Presentation Date: May 11th, 2021
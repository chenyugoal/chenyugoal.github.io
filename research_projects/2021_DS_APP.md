---
layout: page
title:  Shiny APP for Bird Recognition Using Convolutional Neural Network
---

<img src="\research_projects\img\2021_DS\collage.jpg" alt="drawing" width="640"/>

> An easy-to-use [website](https://m250.shinyapps.io/bird_recognition/) 
> for bird image classification.
> Upload a photo (any resolution will be fine) of bird, 
> then it will tell you the top-5 most likely bird species it belongs to.



## Demo

<iframe width="560" height="315" src="https://www.youtube.com/embed/_Ax88Q_l0P4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Dataset & Model

**Caltech-UCSD Birds-200-2011 (CUB-200-2011)** is used as the dataset. 
It contains 11,788 images of 200 bird species, 
including Johns Hopkins's mascot, **Blue Jay!!!!!!**

<img src="\research_projects\img\2021_DS\Johns_Hopkins_Blue_Jays.svg.png" alt="drawing" width="240"/>

To form the classification model, 
the **Resnet-50** and two fully conneted layers are concatenated together. 
The Resnet-50 was pretrained on **ImageNet** by Keras. 
All of its parameters are freezed during training. 
Data augmentation techniques are used, 
including rotation, shifting, shearing, zooming, flipping, 
to avoid overfitting.

On the validation set (20% of the dataset), 
the model achieves an accuracy of ~ 0.35, 
which is far lower than those of the benchmarks. 
The simple and shallow structure of the fully connected layers is to blame. 
I will take some deep learning courses to build a more robust model in the future.

## References

1. https://gerinberg.com/2019/12/10/image-recognition-keras/

2. https://www.r-bloggers.com/2018/02/deep-learning-image-classification-with-keras-and-shiny/

3. https://keras.io/api/applications/
---
layout: page
title:  Progressive Learning - A Potential Algorithm for Lifelong Learning Machines
---

> In biological learning, 
> data are used to improve performance simultaneously on the current task, 
> as well as previously encountered and as yet unencountered tasks. 
> In contrast, classical machine learning starts from a blank slate, 
> or tabula rasa, using data only for the single task at hand. 
> While typical transfer learning algorithms can improve performance on future tasks, 
> their performance on prior tasks degrades upon learning new tasks (called "catastrophic forgetting"). 
> Many recent approaches have attempted to maintain performance given new tasks. 
> But striving to avoid forgetting sets the goal unnecessarily low: 
> the goal of [ProgLearn](https://github.com/neurodata/ProgLearn) is to improve performance 
> on all tasks (including past and future) with any new data.
> 
> [LINK TO THE PAPER](https://arxiv.org/pdf/2004.12908.pdf)

## The Core of ProgLearn

We present an approach to lifelong learning called “omnidirectional learning”. 
Omnidirectional learning algorithms build on the ideas introduced 
in Progressive Neural Networks ([ProgNN](https://arxiv.org/abs/1606.04671)), 
in which new tasks yield additional representational capacity. 
However, although ProgNN’s are able to transfer forwards, 
they fail to transfer backwards. 
Moreover, ProgNN requires quadratic space and time complexity in sample size. 
Our key innovation is the introduction of representation ensembling 
which enables omnidirectional transfer via an “omni-voter” layer, 
reducing computational time and space 
from quadratic to quasilinear (i.e., linear up to polylog terms).

<img src="\research_projects\img\2021_NDD\learning_schema_new.png" alt="drawing" width="800"/>

Schemas of composable hypotheses. 
Ensembling voters is a well-established practice, 
including random forests and gradient boosted trees. 
Ensembling representations was previously used in lifelong learning scenarios, 
but without connections from future tasks to past ones. 
We introduce such connections, thereby enabling backward transfer.
{:.figcaption}

We implement two complementary omnidirectional learning algorithms, 
one based on decision forests (Omnidirectional Forests, Odif), 
and another based on deep networks (Omnidirectional Networks, Odin). 
Both Odif and Odin demonstrate forward and backward transfer, 
while maintaining computational efficiency. 
Simulations illustrate their learning capabilities, 
including performance properties in the presence of adversarial tasks. 
We then demonstrate their learning capabilities 
in vision and language benchmark applications. 
Although the omnidirectional algorithms presented here are primarily resource building, 
we illustrate that they can effectively leverage prior representations. 
This ability implies that the algorithm can convert from 
a “juvenile" resource building state to the “adult" resource recruiting state 
– all while maintaining key omnidirectional learning capabilities and efficiencies.

## Spoken Digit Experiment

After joining the course [Neuro Data Design](https://neurodatadesign.io/) in Fall 2020 semester, 
I became a contributor of this project. 
I first extended the application of ProgLearn to auditory tasks.

I used an audio dataset called [Free Spoken Digit Dataset (FSDD)](https://github.com/Jakobovski/free-spoken-digit-dataset),
and implemented both Odif and Odin. 
Detailed description of the spoken-digit experiment can be found in this [Jupyter notebook](https://github.com/neurodata/ProgLearn/blob/staging/benchmarks/spoken_digit_exp/spoken_digit_exp.ipynb) 

<img src="\research_projects\img\2021_NDD\STFT_digit_0.png" alt="drawing" width="800"/>

Spectrogram extracted from 8 different recordings of 6 speakers uttering the digit ‘0’.
{:.figcaption}

<img src="\research_projects\img\2021_NDD\log_TE_digits_Odif_Odin.png" alt="drawing" width="800"/>

Both Odif and Odin shows positive forward and backward transfer 
for the spoken digit tasks.
{:.figcaption}

## Aircraft-to-Bird Experiment
I further extended the application of ProgLearn 
by using different datasets simultaneously. 
I set up 5 tasks from the [Aircraft dataset](https://www.robots.ox.ac.uk/~vgg/data/fgvc-aircraft/) 
and another 5 tasks from the [Birdsnap dataset](http://thomasberg.org/).
to show that ProgLearn can transfer knowledge not only in one dataset, 
but also across different datasets.

Detailed description of the spoken-digit experiment can be found in this [Jupyter notebook](https://github.com/chenyugoal/ProgLearn/blob/dataset_transfer_exp/docs/experiments/fte_bte_aircraft_bird.ipynb)

<img src="\research_projects\img\2021_NDD\log_TE_airbird_Odif.png" alt="drawing" width="800"/>

Transfer efficiency of Odif.
{:.figcaption}

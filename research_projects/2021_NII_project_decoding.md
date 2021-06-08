---
layout: page
title:  Neural Decoding for Patients with Upper Limb Paralysis
---

> Inspired by the experiment of Elon Musk’s [Neuralink](https://neuralink.com/), 
> where the monkey could play video games with its brain, 
> we implemented two algorithms for neural decoding, 
> the Long Short-term Memory Networks and the Kalman Filter, 
> in our course project of *Neural Implants & Interfaces*.

<iframe width="560" height="315" src="https://www.youtube.com/embed/rsCul1sp4hQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Pager, a nine year old Macaque, plays MindPong with his Neuralink. (www.neuralink.com)
{:.faded} 

## Selected Result
### Kalman Filter

<img src="\research_projects\img\2021_NII\predict_real_KF_05.png" alt="drawing" width="800"/>

Predicted motion (in dashed red) by Kalman Filter and real motion (in blue) of the cursor.
{:.figcaption}

<img src="\research_projects\img\2021_NII\velocity_track_Kalman.gif" alt="drawing" width="480"/>

Motion pursuit - Kalman Filter.
{:.figcaption}

### LSTM

<img src="\research_projects\img\2021_NII\predict_real_LSTM.jpeg" alt="drawing" width="800"/>

Predicted motion (in dashed red) by LSTM and real motion (in blue) of the cursor.
{:.figcaption}

<img src="\research_projects\img\2021_NII\velocity_track_LSTM.gif" alt="drawing" width="480"/>

Motion pursuit - LSTM.
{:.figcaption}

## Presentation

<iframe width="560" height="315" src="https://www.youtube.com/embed/NOyhoJYvcIE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


Speaker: Subhrajit Das, Chenyu Gao, Griffin Mess, Millan Patel

*Neural Implants & Interfaces, Spring 2021*
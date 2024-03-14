# Machine learning for dynamics modeling

## Introduction

As part of my research work at the [CBA lab](https://cba.mit.edu/), I assisted [Jake Read](https://jakeread.pages.cba.mit.edu/) in his work to develop better fabrication machines.

We wanted to develop a machine learning model that predicts the dynamics of a motor given its current state. This repo contains the methods used to create the dataset.

## Data Collection and processing

To create the dataset, we ran a series of measurements using a dynamometer and the motor firmware. The resulting data is a rate time series for each effort value.

Then, we derived acceleration and jerk. The following plots show the resulting data:

<img src='./measurements.png' width=60%/>

 The resulting dataset maps the following input vector to a jerk value, that can later be integrated to state of the system in time ∆t from the previous state:

$$\begin{bmatrix}
Effort_t \\\
Rate_t \\\
Acceleration_t
\end{bmatrix} \rightarrow Jerk_t \rightarrow 
\begin{bmatrix}
Effort_{t+1} \\\
Rate_{t+1} \\\
Acceleration_{t+1}
\end{bmatrix}$$

The following plot shows the 3D relation between the input vector and the output jerk:

<img src='R_A_J_3d.png' width=60%/>

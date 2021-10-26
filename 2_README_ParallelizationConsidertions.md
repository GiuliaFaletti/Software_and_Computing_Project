# Consideration on the parallelization
The codes present in the project must process different plots, which will certainly increase for future analysis. For this reason, I decided to produce both a sequential and a parallelized code, both for the simple production of the plots of the luminosity evolution in Run 2 and the extrapolation plots linked to the proposed model. In both cases, parallelization exploits all the cores present in the computer and processes three processes simultaneously, corresponding to the three years analyzed in Run 2.

## 1) FillsLuminosityEvolution
The code gives the **runtime** (this can change a bit for every run because of the background processes in the cores), which in the sequential case is around 23 seconds, while in the parallelized one is around 7 seconds. This gives a _speedup_ (S) of around 3.3.

## 2) Opt_MeasuredLumi_Extrapolation
The code gives the **runtime** (this can change a bit for every run because of the background processes in the core), which in the sequential case is around 33 seconds, while in the parallelized one is around 11 seconds. This gives a _speedup_ (S) of around 3.

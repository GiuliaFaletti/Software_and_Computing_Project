# Consideration on the parallelization
The codes present in the project must process different plots, which will certainly increase for future analysis. For this reason, I decided to produce both a sequential and a parallelized code, both for the simple production of the plots of the luminosity evolution in Run 2 and the extrapolation plots linked to the proposed model. In both cases, parallelization exploits all the cores present in the computer and processes three processes simultaneously, corresponding to the three years analyzed in Run 2.

## 1) FillsLuminosityEvolution
The code gives the **runtime**, which in the sequential case is around 23 seconds, while in the parallelized one is around 7 seconds. This gives a _speedup_ (S) of around 3.3.

|# Processor|Runtime[s]|Speedup|
|---|---|---|
|1|23||
|2|13.28|S_{1/2}=23/13.28=1.73|
|3|9.61|S_{1/3}=23/9.61=2.39|
|4|8.84|S_{1/4}=23/8.84=2.6|
|5|8.34|S_{1/5}=23/8.34=2.76|
|6|8.22|S_{1/6}=23/8.22=2.798|
|7|8.19|S_{1/7}=23/8.19=2.8|
|8|7.997|S_{1/8}=23/7.997=2.88|



## 2) Opt_MeasuredLumi_Extrapolation
The code gives the **runtime**, which in the sequential case is around 33 seconds, while in the parallelized one is around 11 seconds. This gives a _speedup_ (S) of around 3.

|# Processor|Runtime[s]|Speedup|
|---|---|---|
|1|44||
|2|38.43|S_{1/2}=44/38.43=1.14|
|3|23.83|S_{1/3}=44/23.83=1.85|
|4|16.15|S_{1/4}=44/16.15=2.72|
|5|14.6|S_{1/5}=44/14.6=3|
|6|13.8|S_{1/6}=44/13.8=3.19|
|7|13.336|S_{1/7}=44/13.336=3.3|
|8|12.91|S_{1/8}=44/12.91=3.4|

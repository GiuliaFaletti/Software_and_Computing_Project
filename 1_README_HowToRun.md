# How To Run

## 1) Download the zipped project

You need to download the file from the repository of GitHub.
Click on the green button "Code" and than click on "Download ZIP".

## 2) Extract the project file 

You need some program to unzip the Project.zip folder, if you have a mac 
the utility tool will do the job for you, you just have to click on the zipped file.

## 3) Run the program

Now you are ready to run the program. Enter on the bash the position of the downloaded folder:

'cd path/Software_and_Computing_Project-main/Project'

Then tip on the bash:

- 'python FillsLuminosityEvolution.py' if you want to produce the run 2 luminosity evolution plots;
- 'python FillsLuminosityEvolution_parallel.py' for the parallelized verision;
- 'python Opt_MeasuredLumi_Extrapolation.py' if you want to produce the extrapolated plots for the integrated luminosity optimization;
- 'python Opt_MeasuredLumi_Extrapolation.py' for the parallelized verision

## 4) Looking the results

To observe what the previous codes produce, you can open the ATLAS/FillsLuminosityEvolution{year} folders for the **FillsLuminosityEvolution.py** code and the ATLAS/OptimalFillsLuminosityEvolution{year} for the **Opt_MeasuredLumi_Extrapolation.py** code to observe the produced plots. Moreover, from the latter one there is for the sequential version **Opt_MeasuredLumi_Extrapolation.py** an output excel file, called _Optimized Measured Luminosity.xlsx_, which report the integrated luminosities of each fill and the total luminosities of each year. For the parallelized version **Opt_MeasuredLumi_Extrapolation_parallel.py**, in addition to the folders named above which remain the same, there are the integrated luminosities output files _{year} Optimized Measured Integrated Luminosity.txt_ and the total luminosities output file _RUN 2 Optimized Measured Total Luminosities.txt_.

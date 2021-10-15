# Explanations
Luminosity Extrapolation - Giulia Faletti

## Scope of the code
For my thesis, I'm working on an optimization strategy for the LHC integrated luminosity. The main concepts of this strategy are described in the file *Concepts_of_Integrated_Luminosity_Optimization_Strategy.pdf*. 

In this code, we have an important part of the thesis work, whose aim is to understand what would have happened in reality if the proposed optimization models had been used during LHC run 2.
 From ATLAS instantaneous luminosity measurements, initially, with *FillsLuminosityEvolution.py* (or *FillsLuminosityEvolution_parallel.py*), we plot the luminosity evolution for each fill; secondly, considering the proposed model, implemented in *LuminosityOptimization.py*, some fills are finished sooner than in reality, while others are lengthened (*Opt_MeasuredLumi_Extrapolation.py* or *Opt_MeasuredLumi_Extrapolation_parallel.py*). In the latter case, it was necessary to extrapolate, with a fit, the luminosity evolution in the missing time interval. At the end of the program, the integrated luminosity for each fill and the total luminosity for each year are evaluated. 
 
 This will be fundamental in my work to compare the effective total luminosity of Run 2 and the one that would have been obtained with the strategy proposed in the thesis.

## Organization of the code and description of each file and folder
In the **Project folder** are present different programs, input and output files:

 -------------------------- **Code Files** --------------------------------------------------------------------------------------------------
 
 1. *FillsLuminosityEvolution.py*: Code that extracts from ATLAS_fill_{year} the Luminosity and Time arrays and plots them on the y and x-axis, saving them in FillsLuminosityEvolution{year};

 2. *FillsLuminosityEvolution_parallel.py*: Parallelized code that extracts from ATLAS_fill_{year} the Luminosity and Time arrays and plots them on the y and x-axis, saving them in FillsLuminosityEvolution{year};

 3. *LoadData.py*: Module that defines different functions able to extract data from FillData.xlsx and TurnAroundData.xlsx. It is important to say that the loaded data have been previously cut considering only the turnaround times that can be used for statistical purposes, and the fills defined "physics fills";

 4. *LuminosityOptimization.py*: Module that defines different functions that evaluate the optimization model parameters, like the optimized fill times;

 5. *Opt_MeasuredLumi_Extrapolation.py*: Code that extracts from ATLAS_fill_{year} the Luminosity and Time arrays, compares the length of each fill with the optimal fill time and decides if it is necessary to extrapolate or not. If extrapolation is needed, performs it using a double exponential fit (making sure that the function always decrease). Then the code plots the resulting luminosity evolution in OptimalFillsLuminosityEvolution{year} and evaluates the integrated luminosity for each fill and the total luminosity for each year, saving the results on an excel output file _Optimized Measured Integrated Luminosity.xlsx_;

 6. *Opt_MeasuredLumi_Extrapolation_parallel.py*: Parallelized code that extracts from ATLAS_fill_{year} the Luminosity and Time arrays, compares the length of each fill with the optimal fill time and decides if it is necessary to extrapolate or not. If extrapolation is needed, performs it using a double exponential fit (making sure that that the function always decrease). Then the code plots the resulting luminosity evolution in OptimalFillsLuminosityEvolution{year} and evaluates the integrated luminosity for each fill, saving them in _{year} Optimized Measured Integrated Luminosity.txt_, and the total luminosity for each year, saving them in _RUN 2 Optimized Measured Total Luminosities.txt_.

 --------------------------- **Input Files** ---------------------------------------------------
 
 7. _FillData.xlsx_: Excel file with turnaround times and fill times for each year (t16, tf16, ta17, tf17, ta18, tf18), fills numbers (NrFill_2016, NrFill_2017, Nr_fill2018) and statistical samples of turn around times (sample16, sample17, sample18);
 8. _TurnAroundData.xlsx_: Excel file with sorted statistical samples of turn around times (sample16, sample17, sample18).

 -------------------------- **Output Files** ---------------------------------------------------
 
 9. _Optimized Measured Integrated Luminosity.xlsx_: Excel output file divided into six sheet, three for the integrated luminosities called {year} Integrated Luminosity, and three for the total luminosity called {year} Total Luminosity;
 10. _2016 Optimized Measured Integrated Luminosity.txt_: Output file with 2016 values of integrated luminosity;
 11. _2017 Optimized Measured Integrated Luminosity.txt_: Output file with 2017 values of integrated luminosity;
 12. _2018 Optimized Measured Integrated Luminosity.txt_: Output file with 2018 values of integrated luminosity;
 13. _RUN 2 Optimized Measured Total Luminosities.txt_: Output file with 2016, 2017 and 2018 values of total luminosity.

 -------------------------------- **Data Folder** ---------------------------------------------------
 
 14. ATLAS:
 
 -------------------------- *Input Floders* ---------------------------------------------------
 
 - ATLAS_fill_2016: Atlas lumi files for 2016, whose detailed description is available on [https://lpc.web.cern.ch/MassiFileDefinition_v2.htm].
 - ATLAS_fill_2017: Atlas lumi files for 2017, whose detailed description is available on [https://lpc.web.cern.ch/MassiFileDefinition_v2.htm];
 - ATLAS_fill_2018: Atlas lumi files for 2018, whose detailed description is available on [https://lpc.web.cern.ch/MassiFileDefinition_v2.htm];
 - ATLAS_summary_2016: Atlas summary files for 2016, whose detailed description is available on [https://lpc.web.cern.ch/MassiFileDefinition_v2.htm];
 - ATLAS_summary_2017: Atlas summary files for 2016, whose detailed description is available on [https://lpc.web.cern.ch/MassiFileDefinition_v2.htm];
 - ATLAS_summary_2018: Atlas summary files for 2016, whose detailed description is available on [https://lpc.web.cern.ch/MassiFileDefinition_v2.htm].

 -------------------------- *Output Floders* ---------------------------------------------------
 - FillsLuminosityEvolution2016: Plots of the Luminosity evolution of 2016;
 - FillsLuminosityEvolution2017: Plots of the Luminosity evolution of 2017;
 - FillsLuminosityEvolution2018: Plots of the Luminosity evolution of 2018;
 - OptimalFillsLuminosityEvolution2016: Hypotetical fill plots of the Luminosity evolution of 2016;
 - OptimalFillsLuminosityEvolution2017: Hypotetical fill plots of the Luminosity evolution of 2017;
 - OptimalFillsLuminosityEvolution2018: Hypotetical fill plots of the Luminosity evolution of 2018.

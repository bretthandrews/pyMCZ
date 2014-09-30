MC Metalicity
====================

Monte Carlo method to calculate metalicity uncertainty from flux data.

====================
Usage:
====================
Place the _min, _max, and _med(optional) files in the sn_data folder.


From the commandline simply use as:
```
MCZ_err.py <filename> nsample
```
-\<filename\>: the common filename of the _min and _max files

-nsample: the number of iterations desired


====================
Input file format
====================
each flux data should be stored in the directory sn_data 

with common filename \<fi\>

\<fi\>_max.txt

\<fi\>_min.txt

\<fi\>_med.txt 


where max = med+err, min=med-err. The _med file is optional.

The format for each of the txt files should be as follows:

'''
;# galnum,[OII]3727,Hb,[OIII]4959,[OIII]5007,[OI]6300,Ha,[NII]6584,[SII]6717,[SII]6731,[SIII]9069,[SIII]9532,E(B-V),dE(B-V)
       1     0.0     0.0     0.0     0.0     0.0   5.117   0.998     0.0     0.0     0.0     0.0
       2     0.0     0.0     0.0     0.0     0.0   5.031   1.012     0.0     0.0     0.0     0.0
'''
(example)

galnum is the index used for matching the flux with the corresponding radius for calculating the gradient.

The first row is optional - any row with more strings than numbers will be ignored

the data should be in the above order, separated by any number of white spaces.


====================
Output
====================
All the results will be saved in the directory "\<fi\>" inside "bins"

For a given \<fi\> and nSample, the following output files are generated:

"\<fi\>_n"nSample"_sample.png": the gaussian that was sampled

"\<fi\>_n"nSample"_iX.csv": the metallicity and its uncertainty that was calculated, where X will correspond to the number of rows the input data contains

"hist" folder, containing all the histograms generated


 
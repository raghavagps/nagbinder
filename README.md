# NAGbinder
Prediction of NAG interacting residues

NAGbinder is a Python-based tool for predicting NAG interacting residues in an uncharacterized protein chain. It involves various prediction models developed using machine learning techniques such as, Support Vector Classifier, Random Forest, Artificial Neural Network, which is implemented using Scikit package. These models are developed using features like (i) Binary Profile of patterns and (ii) Evolutionary Information (PSSM) matrix generated using PSI-BLAST.
Residues have the score equal or above the selected threshold are said to be “Interacting” whereas residues showing lesser value than the threshold are considered as “Non-Interacting”. Prediction model developed using binary profiles where Random Forest was implemented, performed best in our study.

# ReferenceAn approach for identifying N-acetylglucosamine interacting residues of a protein from its primary sequence. 
<a href="https://www.ncbi.nlm.nih.gov/pubmed/31654438"> Protein Sci. 2019 Oct 25. doi:10.1002/pro.3761.</a>
## Web Server
https://webs.iiitd.ac.in/raghava/nagbinder/
# Installation

Command for downloading NAGbinder
```
git clone https://github.com/raghavagps/nagbinder
```

NAGbinder is open-source Python-based software, which operates on the Python environment (Python version 3.3 or above) and can run on multi-OS systems (such as Windows, Linux and Mac operating systems). Before running NAGbinder, the user should make sure of all the following packages are available in their Python environment: sys, wget, os, shutil, scipy, numpy(), pandas(), sklearn version 0.19.1, math and re. Installation of Anaconda is recommended, and it is freely available on https://www.anaconda.com/download/ .
The user also needs to download the blastpr folder to run the prediction. Please run the commands given below to download and untar blastpr
**COMMANDS**
```
wget -c http://webs.iiitd.edu.in/gpsr2/blastpr.zip
unzip blastpr.zip
```
# For users who want to do prediction by using our NAGbinder package

```
1. cd nagbinder
2. unzip nag_models.zip
3. python3 nagbinder.py -h
```

# Examples for users to do NAG interacting residue prediction.

The input protein sequence for nagbinder.py should be in fasta format. Please find the example in example folder. The following parameters are required by nagbinder.py

**COMMAND**
```
python3 nagbinder.py -i <input_file> -o <output_file> -m <method> -t <threshold>
```
where,
-       <input_file>: Input file having sequence file in FASTA format
-       <output_file>: Output file generated by NAGbinder having prediction result
- \<threshold>: User defined threshold score (between 0-1)
- \<method>: Machine Learning method and the type of input feature it used
> The value of method can be between 1-6 with each numeral representing the following prediction methods:
>1. Binary SVC
>2. Binary Random Forest
>3. Binary MLP
>4. Binary KNN
>5. PSSM SVC
>6. PSSM Random Forest


### For more information type the following command
```
python3 nagbinder.py –h
```

In our package, we have provided 6 different machine learning models which utilizes different features.
- Method '1' is Support Vector Classifier which utilizes binary profile of the pattern as an input feature.
- Method '2' is Random Forest Classifier which also utilizes binary profile of the pattern as an input feature.
- Method '3' is Artificial Neural Network model developed using binary profile of the pattern as input feature.
- Method '4' is K Nearest Neighbor method developed using binary profile of the pattern as input feature.
- Method '5' is Support Vector Classifier which utilizes evolutionary information in the form of PSSM profile as an input feature.
- Method '6' is Random Forest classifier which also utilizes evolutionary information in the form of PSSM profile as an input feature. The PSSM profile is generated using PSI-BLAST by running against the SwissProt database.

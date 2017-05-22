# LeishBEP
Leishmania specific Linear B-cell epitope prediction 
1. Introduction
   =============
   LeishBEP (Leishmania Specific Linear B-Cell Epitope Predictor) is a perl based open source tool for the prediction of Linear B-cell epitopes that are specific to Leishmani species.
   
2. Installation
   ============
   Linux OS
   (a) Download LeishBEP from github.
   (b) Extract the files to the desired location.
   (c) Provide executable permission to LLBEP file (if it doesn't have executable rights).
   (d) Create folder named "temp" and provide read and write permission to "temp" folder.
   (e) make sure java 1.6 or higher is installed in your system.
   (f) make sure PERL 5.0 or higher version is installed in your system.
   
   Windows and other operating system
   (a) The source code has been writtern in PERL and hence it can be executed as perl script in other operating system. Note: The program is not tested in any other operating system (except Linux based OS) and hence not advised to execute in other OS.

3. Command line options
   ====================
   
   -i : input file in fasta format (mandatory). 
        Note: The option does not validate the FASTA format and hence make sure the input sequence is in fasta format.
   -m : mode  'pep' for peptide (mandatory). 
   -t : threshold for predcition; integer ranging between 0.0 and 1.0 (default 0.6).
   -o : output file (if not mentioned output will be stored in LLBEP_out file).

4. Output Interpretation          
   =====================
   
   (a) A CSV (comma seperated values) file will be generated as output  which contans serial number, peptideheader|input peptide|, and probability score.  .
   (c) The peptides having score greater than threshold mentioned in -t is considered epitopes and such peptides are stored in output file prefixed with "_threshold".

5. Limitations
   ============
   
   (a) Since the models are trained using epitopes and non-epitopes of length >5 and <=24, predictions made for peptides other than these lengths will be undesirable. Hence, it is advised not to input peptides of length less than 6 and greater than 24. 

6. Example
   =======
   (a) ./LLBEP -i test_input_peptides -m pep  -o Test_peptide 
   (b) ./LBEEP -i test_input_peptides -m pep -t 0.5 -o Test_peptide
 	
7. License
   =======
   LBEEP V1.0 is free software; you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation version 3.0 of the License.
   This software is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Lesser General Public License contained in the file LICENSE for more details.

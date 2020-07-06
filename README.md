# Scripts
This package currently includes two scripts for easier analysis/preparation before and after MD simulation. The usage of the two scripts are described below in detail.

## check_trajectory.py
This python program checks the validity of a structure or frames in a trajectory.
The two tested applications of this program are:

    1. when checking the validity of a structure simply do:
  
              python check_trajectory.py --seq SEQUENCE --gro file.gro
   
        where SEQUENCE is the one letter amino acid sequence of the structure with upper 
        caseletter indicating L-amino acid and lowercase letter indicating D-amino acid.
        
        The program will check two things:
        
            a. all omega angles for cis peptide bond. If a cis peptide bond is found, a message will be printed out.
            
            b. the chirality 

## writeBemeta.py

# Scripts
This package currently includes two scripts for easier analysis/preparation before and after MD simulation. The usage of the two scripts are described below in detail.

## check_trajectory.py
This python program checks the validity of a structure or frames in a trajectory.
The two tested applications of this program are:

1. when checking the validity of a structure simply do:
  
              python check_trajectory.py --seq SEQUENCE --gro file.gro
   
   where SEQUENCE is the one letter amino acid sequence of the structure with upper caseletter indicating L-amino acid and lowercase letter indicating D-amino acid.
  
2. when checking the entire trajectory, simply do:
              
              python check_trajectory.py --seq SEQUENCE
              
   note that when using the script in this situation, make sure that there are only relevant gro files as one will be randomly chosen to be used. (An error will be thrown if the gro file does not match with the xtc file. 
     

## writeBemeta.py

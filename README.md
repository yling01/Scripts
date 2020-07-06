# Scripts
This package currently includes two scripts for easier analysis/preparation before and after MD simulation. The usage of the two scripts are described below in detail.

## check_trajectory.py

### Note:
This program has only been tested on head-to-tail cyclic peptide, if you are using program for linear peptide of stapled peptide, please check manually afterwards.

### Program Description
This python program checks the validity of a structure or frames in a trajectory.
The two tested applications of this program are:

1. when checking the validity of a structure simply do:
  
              python check_trajectory.py --seq SEQUENCE --gro file.gro
   
   where SEQUENCE is the one letter amino acid sequence of the structure with upper caseletter indicating L-amino acid and lowercase letter indicating D-amino acid.
  
2. when checking the entire trajectory, simply do:
              
              python check_trajectory.py --seq SEQUENCE
              
   note that when using the script in this situation, make sure that there are only relevant gro files as one will be randomly chosen to be used. (An error will be thrown if the gro file does not match with the xtc file.)
   
The program is also capable of taking the following flags:

              --cutoff: (float) cutoff for a trans peptide bond. The default value is 150, 
                        meaning that a peptide bond is considered as cis if the omega angle 
                        has an absolute value greater than 150 degrees.
                      
              --cyclic: (bool, True or False) flag for head-to-tail cyclic peptide. The default 
                        is True, meaning that the structrue will be treated as a 
                        head-to-tail cyclic peptide when analyzing the structure.
     

## writeBemeta.py
### Note:
This program has only been tested on head-to-tail cyclic peptide, if you are using program for linear peptide of stapled peptide, please check the results manually afterwards.

### Program Description
This program writes the parameter file (filename.dat) for BEMETA simulation.
To run the program, simply do:
              
              python writeBemeta.py [--pdb file.pdb | --gro file.gro]
 
where file.pdb is the structure file in PDB format while file.gro is in GRO format. The program is only able to take one flag. An error will be thrown when both are declared.

The program is also capable of taking the following flags:

              --writeNDX: (bool, True or False) flag for writing out Phi and Psi angles to a 
                          file in NDX format. Default is False.
                          
                          
              --cyclic: (bool, True or False) flag for head-to-tail cyclic peptide. The default 
                        is True, meaning that the structrue will be treated as a 
                        head-to-tail cyclic peptide when analyzing the structure.
                        
              --bemetaName: (string) name of the output file. Default is bemeta.dat
              

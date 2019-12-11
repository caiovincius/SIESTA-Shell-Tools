# SIESTA-Move-Coordinates
A easy way to move all the coordinates from a .xyz file to the input of SIESTA (.fdf file).

## What does this script do?
- First, it will read your input (.fdf file) to identify the numeration of each atomic specie.
- Then, it will replace each atomic specie name inside the .xyz file with its corresponding numeration from the .fdf file.
- Next, it will move all the coordinates from the .xyz to your .fdf file, automatically.
- Additionally, it can change the NumberOfAtoms, NumberOfSpecies and the SystemLabel of the .fdf with the correct values obtained from your .xyz file.

## **How to use?**
1. Copy the script_coord to the folder to the same folder of your .fdf file and .xyz file
2. In the first time you use this script, type the following command before: chmod +x extract_coords
3. Type in the terminal: ./script_coord filename1.fdf filename2.xyz 
     (Alternative mode: ./script_coord filename1.xyz filename2.fdf
6. After that, the coordinates will be moved to the .fdf file, and then, some more options will appear (They are explained below).

## REQUIREMENTS
The name of the pseudopotentials in the block: "%block ChemicalSpeciesLabel" in your * .fdf file must be in one of the following formats: Atom_gga, Atom_lda, or Atom. Ex.: Fe_gga, Fe_lda, Fe.

## Interative Options
- "Rename the SystemLabel with the .xyz filename? (Y)Yes (N)No"

If you choose Yes, the .xyz filename will be placed as the SystemLabel of the .fdf file.

- "Change the NumberOfAtoms in filename.fdf with the correct number of atoms from filename.xyz? (Y)Yes (N)No"

If you choose Yes, the number of atoms inside the .xyz file will be placed as the value of the NumberOfAtoms of the .fdf file.

- "Change the NumberOfSpecies in filename.fdf with the correct number of species from filename.xyz? (Y)Yes (N)No"

If you choose Yes, the number of atomic species inside the .xyz file will be placed as the value of the NumberOfSpecies of the .fdf file.

- "Rename the .fdf filename with the .xyz filename ${nome_xyz_cut}? (Y)Yes (N)No"

If you choose Yes, the .fdf filname will be renamed with the .xyz filename.

## Extras
If you put this script in your Linux PATH, you can use it as a command in any folder, without need to copy it.

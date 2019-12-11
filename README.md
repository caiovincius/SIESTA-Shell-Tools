# SIESTA-Shell-Tools
- A package with many shell-programmed tools to make things easier when you are working on SIESTA. 
- All tools are USER-FRIENDLY, so even a newbie can use it. 
- Some tools are interatives, i.e., some options appear and the user only have to awnser what he/she wants.
 
 A short description of each tool are shown below:

### SIESTA-Extract-Coordinates
A easy tool to extract the initial and final (converged) coordinates from the output (.out) of SIESTA to a .xyz file. This script also work in .fdf files. This script is ideal when you lost the converged .xyz file or you don't know what was the initial structure of the calculation.

### SIESTA-Move-Coordinates
This tool will do the hard work for you, preparing your input (.fdf) through your .xyz file. It will move all the coordinates from .xyz and replace the atoms labels with the atoms numbers in the .fdf. Also, it can change the SystemLabel, NumberOfAtoms, NumberOfSpecies and rename your .fdf with .xyz name, automatically!

### SIESTA-Move-Coordinates

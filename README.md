# SIESTA-Shell-Tools
- A package with many shell-programmed tools to make things easier when you are working on SIESTA. 
- All tools are USER-FRIENDLY, so even a newbie can use it. 
- Some tools are interatives, i.e., some options appear and the user only have to awnser what he/she wants.
 
 A short description of each tool are shown below:

### SIESTA-PDOS-Utility
This is a very interactive tool that will generate a .dat or .agr file containing the PDOS of your system. The .agr file is compatible with the xmgrace software. In addition, this tool is fully customizable with many options, where you cam separate the energy levels between some atoms, exclude some energy levels from some atoms and more. This script really does everything automatically, so it's very powerful tool.

### SIESTA-Mulliken-Population-Utility
This tool will calculate the Mulliken Population per atom specie from the output (.out) of SIESTA. It is fully customizable, where you can sum over only some atoms, substract from some pre-defined value and so on.

### SIESTA-Band-gap-Calculation
This script will calculate the band-gap of all the .bands files you have in the folder, i.e., it is a massively and accurate way to calculate the band-gap of your systems.

### SIESTA-Move-Coordinates
This tool will do the hard work for you, preparing your input (.fdf) through your .xyz file. It will move all the coordinates from .xyz and replace the atoms labels with the atoms numbers in the .fdf. Also, it can change the SystemLabel, NumberOfAtoms, NumberOfSpecies and rename your .fdf with .xyz name, automatically!

### SIESTA-Extract-Coordinates
A easy tool to extract the initial and final (converged) coordinates from the output (.out) of SIESTA to a .xyz file. This script also work in .fdf files. This script is ideal when you lost the converged .xyz file or you don't know what was the initial structure of the calculation.

### SIESTA-Test-Lattice
An easy tool to replicate your structure from the .xyz file using the LatticeConstant and LatticeVectors that you choose. Thus, you can test if your Lattice parameters are correct for your periodic calculation in SIESTA.

### RHO2XSF-LDOS-Utility
It dysplays on terminal the parameters: SystemLabel, Fixed Origin (in Bohr), the 3 Spanning Vectors (in Bohr) and the correct grid points number of your system, so it makes the things easy for you plot the LDOS on RHO2XSF script

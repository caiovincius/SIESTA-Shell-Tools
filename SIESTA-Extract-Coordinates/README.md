# SIESTA-Extract-Coordinates
A easy tool to extract the initial coordinates of your input (.fdf) or output (.out) from SIESTA into a .xyz file format

## What does this script do?
- If you need to verify what was the initial structure of a .fdf or .out file of the SIESTA COMPUTATIONAL PACKAGE. Or if you don't know where is your .xyz with the converged structure, this tool can extract both the initial and converged coordinates from a .out file to a .xyz file, in a very easy way.

## **How to use?**
1. Put the extract_coords at the same folder of your .out or .fdf file that you want to extract the coordinates.
2. In the first time you use this script, type the following command before: chmod +x extract_coords
3. Type in the terminal: ./extract_coords filename.out --options
./extract_coords filename.fdf

## OPTIONS
-     --initial or -i: Extract the initial coordinates from the .out file.
-     --converged or -c: Extract the converged coordinates from the .out file.
-     --version or -v: Show the version.
-     --help or -h: Show the help.

## Extras
If you put this script in your Linux PATH, you can use it as a command in any folder, without need to copy it.

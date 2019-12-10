# SIESTA LATTCE TEST
An easy tool to replicate your structure (.xyz file) in the directions X, Y and Z, using your LatticeConstant and LatticeVectors.

## What does this script do? 
This script will replicate your structure in the directions you choose. Thus, you can test if your LatticeConstant and LatticeVectors are correct before you perform the calculation at SIESTA.
Moreover, if you only want increase your structure size, this script do this work too in a very easy way.

## How to use?
- Copy this script to your .xyz file folder.
- And enter the correct lattice information of your structure (LatticeConstant and LatticeVectors).
- In terminal, type the command: ./script_replic filename.xyz
- If any error occurs, type the following command: chmod +x script_replic

## Extra
You can add this script in your linux PATH, thus you can use this as a command in any folder, without need to copy it

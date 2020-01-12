# RHO2XSF-LDOS-Utility
An easy tool to calculate the correct parameters of your system to plot the LDOS without any errors, using the RHOS2XSF script.

## WHAT DOES THIS SCRIPT DO? 
It dysplay on terminal the parameters: SystemLabel, Fixed Origin (in Bohr), the 3 Spanning Vectors (in Bohr) and the correct grid points number of your system, so it makes the things easy for you plot the LDOS on RHO2XSF script.

## WHY TO USE THIS SCRIPT?
Sometimes the LDOS plot cause some errors like some atoms move to the opposite side an so on. With this script, any of this errors will happen, because all the parameters are calculated using your converged structure.

## HOW TO USE?
- Copy this script to your calculation folder. Verify if you have the .XV, .xyz and .LDOS files.
- Type in the therminal the following command: ./ldos_params
- If you get any error, type in the terminal: chmod +x ldos_params

## Extra

You can add this script in your linux PATH, thus you can use this as a command in any folder, without need to copy it.

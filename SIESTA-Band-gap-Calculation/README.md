# SIESTA-Band-gap-Calculation
An easy tool to calculate the band-gap of .bands file generated from calculation using SIESTA.  You can do this massively by copying many .bands files to the same folder and running the script.

## WHAT DOES THIS SCRIPT DO? 
It calculates the band-gap energy through the .bands file. If you have many .bands file in a folder, it will calculates the band-gap energy for ALL the .bands file.

## HOW TO USE?
- Copy this script to your calculation folder that contains the .bands file. Or copy all of your .bands file to the same folder and put this script there.
- Type in the therminal the following command: ./calc_gap
- If you get any error, type in the terminal: chmod +x calc_gap

## Options

"Do you want verify if the band-gap is direct or indirect (EXPERIMENTAL)? (Y)Yes (N)No"

If you choose yes, the script will try to verify if the band-gap is direct or indirect. BUT, this is a EXPERIMENTAL section, sometimes it will show the wrong awnser. In the future, we will try to improve the algorithm to get a better precision in differentiating a direct gap from a indirect gap. Nevertheless, this script will calculate the band-gap in a very precise way.


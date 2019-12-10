# SIESTA Mulliken-Population-Utility
An easy tool to calculate Mulliken Population in many customized ways for SIESTA Calculations.

## WHAT DOES THIS TOOL DO:
It calculates the Mulliken Population for each atom specie from the .out file generated in calculations using SIESTA.

## USAGE:
- Copy this script to the .out file folder.
- Type in therminal: ./calc_pop filename.out --options
- If you get any error, type: chmod +x calc_pop

## OPTIONS:
- -u or --until: Calculate the Mulliken Population until the specified atom number in the system.
- -s or --sum: Sum the population of two or more atom species. Syntax: Separate the atom species number with ':'. Ex.: ./calc_pop filename.out -s 1:2 \n
- -v or --value: Substract the result of the option -s or --sum from a specified value.
- -h or --help: Show the help.
- -V or --Version: Show the help"

## EXAMPLES:
- Calculate until atom 80, sum the 1st, 3rd and 4th atom species population, and substract 320.20 from the sum:

./calc_pop filename.out -u 80 -s 1:3:4 -v 320.20

## Extras
If you put this script in your Linux PATH, you can use it as a command in any folder, without need to copy it.

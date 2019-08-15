# SIESTA-PDOS-Utility
A easy tool to make PDOS in SIESTA, if you want to know how to do PDOS very easy and fast, this tools is for you!

What does this script do?
- It will easy generate a PDOS (Projected Density of States) with the Fermi level for you calculation done on SIESTA Package. You can also separate the energy levels of repeated atoms in your system and customize your graph before plot in xmgrace.

How to use?
In the first time you use this script do this:
1- Copy the script_PDOS_plot to the folder Util/pdosxml (It is located inside your SIESTA folder).
2- Open a terminal in this folder and type the following command: chmod +x script_PDOS_plot
(Only do the steps 1 and 2 in the first time you use this script)
3- Copy the .PDOS and .bands files to the folder Util/pdosxml (It is located inside your SIESTA folder).
4- Be sure that only has one .PDOS and .bands file in this folder.
5- Open a terminal in this folder and type the following command: ./script_PDOS_plot
6- Follow the steps that will appear! 

Options:
- The First option that will appear is:
"Do you want to separate each energy level from each atom? (Y)Yes (N)No"
If you choose Yes, new options will appear for you choose the atom you want (Ex.: Fe, C_gga, Mn_lda... Enter the specie name that appear), and then the energy level you want (Ex.: 2s, 3p, 4f, 3, 5... You can enter only the n quantum number or the n and l quantum numbers). After that, the tool you ask if you want to plot more energy levels and you can choose as many as you want. If you don't wanna, type 0.
If you choose No, the script will not plot all energy levels together of each atom of your system.

- The Second option that will appear is:
"Do you want to customize your chart for xmgrace? (Y)Yes (N)No"
(EXPERIMENTAL OPTION)
If you like to plot your graph in xmgrace, this option is for you, this tool will customize your graph for you automatically.
If you choose Yes, new options will appear asking you for the X_min, X_max, Y_min and Y_max values to cut your graph. After that, you will be asked to enter the color of each line, and a .agr file will be generated after this script do its work.

- The Second option that will appear is:


# SIESTA-PDOS-Utility
A easy tool to make PDOS in SIESTA, if you want to know how to do PDOS very easy and fast, this tools is for you!

## What does this script do?
- It will easy generate a PDOS (Projected Density of States) with the Fermi level for you calculation done on SIESTA Package. You can also separate the energy levels of repeated atoms in your system and customize your graph before plot in xmgrace.

## **How to use?**
1. Copy the script_PDOS_plot to the folder Util/pdosxml (It is located inside your SIESTA folder).
2. Open a terminal in this folder and type the following command: chmod +x script_PDOS_plot
   - (Only do the steps 1 and 2 in the first time you use this script)
3. Copy the .PDOS and .bands files to the folder Util/pdosxml (It is located inside your SIESTA folder).
4. Be sure that only has one .PDOS and .bands file in this folder.
5. Open a terminal in this folder and type the following command: ./script_PDOS_plot
6. Follow the steps that will appear! 

Options:
- The First option that will appear is:
"Do you want to separate each energy level from each atom? (Y)Yes (N)No"
If you choose Yes, new options will appear for you choose the atom you want (Ex.: Fe, C_gga, Mn_lda... Enter the specie name that appear), and then the energy level you want (Ex.: 2s, 3p, 4f, 3, 5... You can enter only the n quantum number or the n and l quantum numbers). After that, the tool you ask if you want to plot more energy levels and you can choose as many as you want. If you don't wanna, type 0.
If you choose No, the script will not plot all energy levels together of each atom of your system.

- The Second option that will appear is:
"Do you want to customize your chart for xmgrace? (Y)Yes (N)No"
(EXPERIMENTAL OPTION)
If you like to plot your graph in xmgrace, this option is for you, this tool will customize your graph with subtitles for each state automatically, colors and many others features that will choose.
If you choose Yes, new options will appear asking you for the X_min, X_max, Y_min and Y_max values to cut your graph. After that, you will be asked to enter the color of each line, and a .agr file will be generated after this script do its work.

- The Third option that will appear is:
"Do you want to split the PDOS from some atom? (Y)Yes (N)No"
This option is useful if your system have two compunds constituted with the same atoms. Ex.: Carbon Nanotube interacting with Ethanol molecule, so both compounds have carbon atoms, with this option you can separate the carbon atom states from the nanotube and the ethanol molecule. 
For this, you have to certify yourself that the atoms coordinates of the ethanol molecule is after or before the carbon nanotube coordinates in your SIESTA input. Ex.: If you have a carbon nanotube with 80 atoms and the coordinates of the ethanol is located after the nanotube, so from atom 81 onwards is only the ethanol molecule. Thus, you can split the PDOS after the 81 atom to separate the carbon states of both compounds. 
Hence, in this option you have to enter from which atom you want to separate the states. You can also separate the states from X atom until Y atom and from Y atom until Z atom, as many atoms as you want. Ex.: 81 to 90 to 95 to 101...
Note: Basically, what the tool wil do is split the PDOS from the atom X to atom Y, and then it will compare the two files, if a repeated specie is found, it will extract them separately and will put a different subtitle in these states (Ex.: Substitle C(1) for carbon states of the nanotube and C(2) of the ethanol), the others states will be extracted normally.

After you choose all the options you want, this tools will:
- Create a folder with your System Label
- Move your .PDOS and .bands files for the created folder
- Generate a .dat file called PDOS-YOUR_SYSTEMLABEL.dat with your PDOS graph.
- Generate a .dat file called Fermi-Level.dat with you Fermi Level coordinates to be imported in your PDOS graph.
- If you choose to customize your graph for xmgrace, a .agr file will be generated and automatically will be openned in your xmgrace.
- If you DO NOT choose to customize your graph for xmgrace, a table with the order of each state will be shown in your terminal. Ex.: 
    ```
    1º State: C
    2º State: N_2s
    3º State: N_2p
    4º State: H(1)
    5º State: H(2)
    ```

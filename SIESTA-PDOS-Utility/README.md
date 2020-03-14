# SIESTA-PDOS-Utility
A easy tool to make PDOS in SIESTA, if you want to know how to do PDOS very easy and fast, this tool is for you!

## What does this script do?
- It will easy generate a PDOS (Projected Density of States) with the Fermi level for you calculation done on SIESTA Package. You can also separate the energy levels of repeated atoms in your system and customize your graph before plot in xmgrace.

## **How to use?**
1. Copy the script_PDOS_plot to the folder Util/pdosxml inside the SIESTA folder.
2. Type the following command in the terminal: chmod +x script_PDOS_plot
   - (Only do the steps 1 and 2 in the first time you use this script)
 3- Copy your .PDOS and .bands files to the folder Util/pdosxml
 4- Run the script: ./script_PDOS_plot --options

## Modes:
- There are two modes to run this script:
   1. Interactive mode:
                   ./script_PDOS_plot file1.PDOS file2.bands
   2. Terminal commands mode:
                   ./script_PDOS_plot file1.bands file2.PDOS --options

   If you choose the interactive mode, a lot of options will appear and you
   have to select what do you want to do. While the terminal commands mode, as
   all the options are selected with only one command line, the calculation
   will be done immediately

####      Important: If you don't use any terminal command options, the script will automatically start the INTERACTIVE MODE.

## Terminal Commands

- The First option that will appear is:
- -s or --species:   Choose which atom species with its corresponding energy
                   levels will be plotted. If you want all the energy levels
                   of an atom, don't specify them.
                   Syntax: ATOM:ATOM-2s:ATOM_gga-2p:ATOM-3...
                           all (all atom species without separating their
                                energy levels)
-    -f or --fermi:     Change the Fermi Level to another value, such as 0, -2...
-    -c or --cut:       Split the PDOS from some atom until another. Useful in
                   systems which have 2 compounds with the same atoms, for
                   example: Carbon nanotube with Ethanol.
                   Syntax: INTEGER-INTEGER-INTEGER-INTEGER...
                   (Only positive integers)
-    -xmg or --enable-xmg:
                   A .agr file, compatible with the xmgrace software, will
                   be generated with the correct labels and subtitles.
                   The X and Y Axis values have to be definied by the user,
                   so you must use the options -x and -y after this option.
-    -x:              Specify the minimum and maximum values for the X Axis,
                   respectively.
                   Syntax: REAL:REAL
-    -y:              Specify the minimum and maximum values for the Y Axis,
                   respectively.
                   Syntax: REAL:REAL
-    -V or --version: Show The version
-    -h or --help: Show the help

## Interactive Options

- "Do you want to separate each energy level from each atom? (Y)Yes (N)No"

     - If you choose Yes, new options will appear and you have to enter the atom specie you want (Ex.: Fe, C_gga, Mn_lda...), with the orbital separated by "-" (Ex.: Fe-3s, Fe-3p, C_gga-2p, Mn_lda-4f, N-2, Cl_gga-3...) 
     - If you don't want to separate the energy levels for each orbital of an atom specie, enter only the atom specie without the orbital. 
        - If you choose No, the tool will plot all energy levels together for each atom specie.

- "Do you want to customize the PDOS plot to the xmgrace format (it generates an .agr file)? (Y)Yes (N)No"
(OPTIONAL)
     - If you like to plot graphs in xmgrace, you can use this option to generate an .agr file with all the subtitles for each energy state.
     - If you choose Yes, new options will appear asking you to enter the minimum and maximum values for the X and Y axis, and the colors you want (in the latter, you can use the default colors). 
     - If you choose No, a .dat file will be generated, and the corresponding subtitles for each energy state will appear in the terminal.

- "Do you want to split the PDOS from some atom? (Y)Yes (N)No" 
      - This option is useful if the system have two compunds constituted with the same atoms. Ex.: Carbon Nanotube interacting with Ethanol molecule, so both compounds have carbon atoms, with this option you can separate the carbon atom states of the nanotube from carbon atom states of the ethanol molecule.   
      - Certify yourself that the atoms coordinates of the compound 1 is after or before the atom coordinates of the compound 2 in your SIESTA input. 
            - Ex.: If you have a carbon nanotube with 80 atoms and the coordinates of the ethanol is located after the nanotube, so from atom 81 onwards is only the ethanol molecule. Thus, you can split the PDOS after the 81 atom to separate the carbon states of both compounds. 
Hence, in this option you have to enter from which atom you want to separate the states. You can also separate the states from X atom until Y atom and from Y atom until Z atom, as many atoms as you want. Ex.: 81 to 90 to 95 to 101...
Note: Basically, what the tool wil do is split the PDOS from the atom X to atom Y, and then it will compare the two files, if a repeated specie is found, it will extract them separately and will put a different subtitle in these states (Ex.: Substitle C(1) for carbon states of the nanotube and C(2) of the ethanol), the others states will be extracted normally.

## What will be done?
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
- If you choose to split the PDOS from some atom and repeated species were found, a different subtitle will be done for these states automatically in the generated .agr file, if you chooose to customize the graph for xmgrace, if not the subtitles will appear with different names for the repeated species, for example the 4º and 5º State in the example above for hydrogen.

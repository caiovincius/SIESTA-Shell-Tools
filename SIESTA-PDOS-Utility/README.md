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

     - If you like to plot graphs in xmgrace, you can use this option to generate an .agr file with all the subtitles for each energy state.
     - If you choose Yes, new options will appear asking you to enter the minimum and maximum values for the X and Y axis, and the colors you want (in the latter, you can use the default colors). 
     - If you choose No, a .dat file will be generated, and the corresponding subtitles for each energy state will appear in the terminal.

- "Do you want to split the PDOS from some atom? (Y)Yes (N)No"

     - This option is useful if the system have two compunds constituted with the same atoms. Ex.: Carbon Nanotube interacting with Ethanol molecule, so both compounds have carbon atoms, with this option you can separate the carbon atom states of the nanotube from carbon atom states of the ethanol molecule.
     
     - Basically, what the tool wil do is split the PDOS from the atom X to atom Y, and then it will compare the two files, if a repeated specie is found, it will extract them separately and will put a different subtitle in these states (Ex.: Substitle C(1) for carbon states of the nanotube and C(2) of the ethanol), the others states will be extracted normally.
     
     - Certify yourself that the atoms coordinates of the compound 1 is after or before the atom coordinates of the compound 2 in your SIESTA input. 
          - Ex.: If you have a carbon nanotube with 80 atoms and the coordinates of the ethanol is located after the nanotube, so from atom 81 onwards is only the ethanol molecule. Thus, if you choose Yes, type 80 to split the PDOS after the 80 atom to separate the carbon states of both compounds.       

     - You can also separate the states from X atom until Y atom and from Y atom until Z atom, as many atoms as you want. Ex.: 80 to 89 to 95 to 101...

- "Do you want to change the Fermi Level to another value? (Y)Yes (N)No"

     - If you choose Yes, type the value you want to change the Fermi Level.
     
          - All energy states will be moved to set the Fermi level at the specified value.
          
     - If you choose No, the Fermi Level of the system will remain the same.

## What will be done?
- A folder with your System Label name will be created, and the .PDOS, .bands and al of the generated files will be moved to this folder.
- If you chose to customize the PDOS for the xmgrace format or used the options: -xmg or --enable-xmg, a .agr file called PDOS-YOUR_SYSTEMLABEL.agr wil be generated.
- If you don't chose to customize the PDOS for the xmgrace format or didn't use the options: -xmg or --enable-xmg, a .dat file called PDOS-YOUR_SYSTEMLABEL.dat wil be generated, and the subtitles for their corresponding values will be shownappear in the terminal. Ex.: 
    ```
    1º State: C
    2º State: N_2s
    3º State: N_2p
    4º State: H(1)
    5º State: H(2)
     ```
- If you choose to split the PDOS from some atom and repeated species were found, a different subtitle will be generated for these states automatically in the generated .agr file. However, in the case of the .dat file, the subtitles will appear with different names for the repeated species in the terminal (Look the 4º and 5º states in the example above).

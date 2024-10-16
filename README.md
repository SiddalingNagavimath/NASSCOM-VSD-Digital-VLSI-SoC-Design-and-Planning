# NASSCOM-VSD-Digital VLSI SoC Design and Planning
## Open-source EDA, OpenLANE and Sky130 PDK
## Introduction


  Open-Source EDA (Electronic Design Automation)➡️ refers to the movement towards making EDA tools and resources freely available to the public. This democratizes access to advanced design tools, allowing everyone to make use of it 

  OpenLANE➡️ is an automated RTL (Register-Transfer Level) to GDSII (Graphic Database System II) flow2
. It integrates several open-source tools like OpenROAD, Yosys, Magic, Netgen, and custom scripts for design exploration and optimization2
. OpenLANE aims to simplify and automate the physical design process, making it accessible to a broader audience

Sky130 PDK (Process Design Kit)➡️ is an open-source PDK provided by SkyWater Technology Foundry in collaboration with Google and Efabless4
. It is based on SkyWater's 130nm CMOS technology and offers designers worldwide free access to chip design technology to create manufacturable designs4

## Inception of open-source EDA, OpenLANE and Sky130 PDK

![core and die](https://github.com/user-attachments/assets/2ca224f5-e409-45c3-89be-0999db08200a)
### - Die,pad,core
In VLSI design, the die pad core refers to the region on a semiconductor die that includes the pads used for electrical connections to the external environment. These pads serve as interfaces for power, ground, and signal lines, facilitating communication between the chip and other components or systems. Proper design of the die pad core is crucial for ensuring reliable connections, minimizing parasitic effects, and optimizing the overall performance of the integrated circuit. Additionally, the layout and arrangement of the die pads are key factors in achieving efficient packaging and heat dissipation.
______
![Screenshot](https://github.com/user-attachments/assets/8ab89589-2d39-43d7-b621-51d70e265a73)
### Flow-

The image explains the flow of designing a RISC-V CPU:

1. **RISC-V Code**: Starts with writing high-level C code (like the `swap` function), which is compiled into RISC-V assembly using tools like `riscv64-unknown-elf-objdump`.

2. **picorv32 CPU Core Implementation**: The assembly code is executed by the `picorv32`, a minimal RISC-V CPU core. The Verilog code snippet shows how the CPU core processes instructions, controls registers, and manages data flow.

3. **Layout (qflow)**: Finally, the hardware design, represented by the `picorv32` core, is mapped onto a physical layout using the qflow tool. This layout is a visual representation of how logic gates and circuits are arranged on the silicon chip.

The flow illustrates how high-level code is translated into assembly, then implemented in a CPU core, and finally physically laid out for fabrication.
____
### Physical design flow
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/rtl%20to%20gds%20flow.png)

In the RTL to GDS flow, physical design is the critical stage where the synthesized netlist, design constraints, and standard cell library are used to create a layout (GDS file) that follows foundry-specific design rules. This layout is then sent to the foundry for chip fabrication.

Physical design includes several stages, each requiring mandatory checks, analysis, and verification to ensure the layout meets all technical requirements before manufacturing.
___
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(42).png)
___
### Asic flow
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(43).png)

OpenLane is an open-source ASIC design flow that automates the process of turning RTL designs into a final GDSII layout, ready for fabrication. It integrates various open-source tools to handle different stages of the flow, including synthesis, floorplanning, placement, routing, and verification.

## Easy access for Sections
- [SECTION 1](#Section-1)
- [SECTION 2](#Section-2)
- [SECTION 3](#Section-3)
- [SECTION 4](#Section-4)
- [SECTION 5](#Section-5)

## Section 1 
### Inception of open-source EDA, OpenLANE and Sky130 PDK
Tasks to be Completed:-
- [TASK 1:-](Run'picorv32a'designsynthesisusingOpenLANEflowandgeneratenecessaryoutputs)
- [TASK 2:-](2.Calculating-Flop_Ratio(D_flipflop))

____
1.Run 'picorv32a' design synthesis using OpenLANE flow and generate necessary outputs.
2.Calculate the flop ratio.

#### 1. Run 'picorv32a' design synthesis using OpenLANE flow and generate necessary outputs.

Invoking the OpenLANE_flow and Run synthesis 
```
# Change directory to openlane flow directory
 cd Desktop/work/tools/openlane_working_dir/openlane

# alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e 
PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
# Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
```
```
# Now that we have entered the OpenLANE flow contained docker sub-system we can invoke the OpenLANE flow in the Interactive mode using the following command
./flow.tcl -interactive

# Now that OpenLANE flow is open we have to input the required packages for proper functionality of the OpenLANE flow
package require openlane 0.9

# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

# Exit from OpenLANE flow
exit

# Exit from OpenLANE flow docker sub-system
exit

```
Screenshots of executed commands

![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/VirtualBox_vsdworkshop_08_10_2024_23_56_32.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/run_synthesis%20complete.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/yosus%204%20synthesis%20report.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/VirtualBox_vsdworkshop_08_10_2024_23_58_23.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/VirtualBox_vsdworkshop_09_10_2024_00_01_18.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/cell_level%20lef%20info.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/pdk%20used%20by%20run%20etc.png)

#### 2.Calculating Flop_Ratio(D_flipflop):-  
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/dff%20flop%20ratio.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/dff%20flop%20ratio%20ans.png)                     

**total no.of cells**=14876                                                                 
**no.of d_ff**=1613                                                                     
**flop_ratio**=(1613/14876)=0.1084296853993009                                        
**Percentage**= flop_ratio*100=10.84296853993009%







## Section-2
#### Good floorplan vs bad floorplan and introduction to library cells

#### 1. Run 'picorv32a' design floorplan using OpenLANE flow and generate necessary outputs.
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(48).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(49).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(51).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(53).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(54).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(55).png)

```
#### Increement or Decreement of Ioplace cells
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/incre_or_decree%20in%20size%20of%20ioplacecell.png)

#### Location of Global and Local Variable
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/Global%26local%20variable%20in%20readme.png)

#### Core utilisation
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/core%20utl%20overriden%20by%20pdk%20specific%20configtcl.png)

#### def file of floorplan
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/def%20file%20of%20floorplan.png)

#### 2.Floorplan Def file gives the values of ..                                                  
Die width in units=660685/1000=660.685 (in microns)                                           
Die height in units=671405/1000=671.405                                                       
//let's find the Area                                                   
Area of Die = 660.685*671.405 = 443587.212425 square microns

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/floorplan%20variable.png)

####  3.Open a new terminal to load the generated floorplan definition in the Magic tool and explore the layout.

```
//Change directory to newly generated floorplan def file
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/11-10_06-41/results/floorplan/

// command to run floorlan def file in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```
Screenshot of Floorplan def file in magic  
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/Magic%20opening.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/magic%20placement.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/magic_io_metal.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/op%20of%20size%20ioplace.png) 

#### 4.Run 'picorv32a' design congestion aware placement using OpenLANE flow and generate necessary outputs.
```
//Command to run in openlane working flow
run_placement
```
### 5.Load generated placement def in magic tool and explore the placement.
#### Commands to load placement def in magic in New terminal
```
// change directory to newly generated placement file in another terminal
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/11-10_06-41/results/placement/

// command to run placement def fie in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

```
#### screenshot of placement def in magic
![313492838-e703ef0b-3968-4132-a9c7-05b53f50b214](https://github.com/user-attachments/assets/8e0c512f-f8dc-410e-b1cd-df4d9a6f32b8)

```
command to exit in the openflow
exit
exit
```
## Theory
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(57).png)

It defines the Pin placement location and proper Arrangement
___
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(59).png)
Glimpse of the Library Characterization and modelling
___
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(86).png)
Static Behaviour Evaluation Of CMOS inverter
___
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(89).png)
glimpse of Active region making process for 16 mask CMOS 

## Section 3
#### Design library cell using Magic Layout and ngspice characterization

##### 1.Cloning the custom inverter standard cell design from github repo
```
change directory to openlane
cd Desktop/work/tools/openlane_working_dir/openlane

enter command to clone github repo
git clone https://github.com/nickson-jose/vsdstdcelldesign

after cloning change directory
cd vsdstdcelldesign

copying the Magic tech file in vsdstdcelldesign
cp /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech 

command to open custom inverter design in magic tool
magic -T sky130A.tech sky130_inv.mag &
```
#### Execution of commands
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/gitclone.png)

#### 2. Load the custom inverter layout in magic and explore.
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/layout%20for%20cmos%20inverter%20by%20git%20clone.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/location%20of%20n%26p%20mos%20in%20cmos.png)

#### Difference between layout and lef file
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/show%20what%20s%20layout%20and%20lef.png)


![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/copied%20from%20magic%20(sky130a).png)

#### 3.Spice extraction of inverter in Magic
Commands to run in tkcon terminal of magic tool
```
command to check directory in which you are present
pwd

command to run for extraction of file to .ext format
extract all

command to enable parasitic Extraction
ext2spice cthresh 0 rthresh 0

command to convert ext to spice file format
ext2spice
```
Execution of commands

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/ext%20and%20spice%20file%20create.png)

#### Ext2spice file creation
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/ext2spice%20file%20creation.png)

#### Circuit for inv.ext file
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/circuit%20for%20inv_ext%20file.jpeg)

#### 4. Editing the spice model file for analysis through simulation.
#### Spice file created from ext file which acts as input for the ngspice simulation
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/ngspice%20input.png)

#### 5. Post-layout ngspice simulation
#### Commands for ngspice simulation
```
//Command to directly load a SPICE file for simulation in Ngspice
ngspice sky130_inv.spice

//Now that we’ve entered Ngspice with the simulation SPICE file loaded, we just need to display the plot.
plot y vs time a
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/values%20obtained%20from%20ngspice.png)
#### Screenshot of generated plot
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/output%20vs%20time%20in%20transition.png)

```
//Rise transition time calculation
Rise transition time = time taken for o/p to rise to 80% - time taken for i/p to rise to 20%
20% of output = 660mV 
80% of output = 2.64
```

#### 20% Screenshots
![314002633-261c420f-219f-4c26-ae32-6c0db82a722e](https://github.com/user-attachments/assets/487b7b0c-c147-4e63-9720-319fe4f3d206)
![314004259-bbb078c4-b3aa-436b-8832-23e5d7777081](https://github.com/user-attachments/assets/50ad862b-3b5e-446d-b376-719415dc38a9)

#### 80% Screenshots
![314005593-d10a0ff1-0523-4fe4-96f4-eefc63f647f7](https://github.com/user-attachments/assets/df736a2f-2815-49a1-b96f-9017e6365f70)
![314005616-929042ad-2032-49aa-ae07-2a2163b9603e](https://github.com/user-attachments/assets/b7d40f73-5f07-4f72-9a81-6b2a3c21587e)

Rise transition time =2.24638-2.18242=0.06396ns=63.96ps  

```
# Fall transition time calculation
Fall transition time = Time taken for output to fall to 20% - Time taken for output to fall to 80%

```
![314009074-0180052c-4b8c-4bd8-928c-cd8ab34d5a17](https://github.com/user-attachments/assets/cdfa26ea-0499-42c2-b047-1d19f1f392a5)
![314009104-83760cf7-18c9-45d1-8063-04baafe1dd1f](https://github.com/user-attachments/assets/492503ce-714e-4773-ba21-b2440c600324)
![314009811-7bc0eeee-c7cd-464e-a90b-cac8d4f83144](https://github.com/user-attachments/assets/fb2bdd0b-4435-4bd3-be76-a2d89468e57e)
![314009833-9a7dc3b0-9936-4704-97cd-1cd03cc6a8cb](https://github.com/user-attachments/assets/34ab4ef6-ddd0-438a-bda2-c968bc80e6d5)

Fall transition time = 4.0955-4.0536=0.0419ns=41.9ps 

```
# Rise Cell Delay Calculation

Rise cell delay=Time taken for output to rise to 50% - Time taken for input to fall to 50%
```
50% of 3.3 V =1.65 V

50% Screenshots
![314018565-e34363cd-a70f-4939-b8e5-efb10620ce93](https://github.com/user-attachments/assets/e592a4d2-ecb8-4b88-a9cb-5a2c5cf3f0d7)
![314018583-f7452b60-3612-4bcf-a71d-b8ff021d5297](https://github.com/user-attachments/assets/3a965710-8d86-4511-8359-ce3f68f84f15)

Rise cell delay =2.21144-2.15008=0.06136ns=61.36ps 

```
Rise cell delay=Time taken for output to fall to 50% - Time taken for input to rise to 50% 
```
50% Screenshots
![314020455-3d2ff2e5-dab6-497a-b5a4-74959f69c2a2](https://github.com/user-attachments/assets/85c3ac09-2cad-4e22-9126-d040f7bc1e69)
![314020467-aa88c26b-0cc4-4cf7-80d7-b2058e8fbc47](https://github.com/user-attachments/assets/76894af9-8929-48b3-bee3-75201e824c6b)

Fall Cell Delay = 4.07-4.05 = 0.02 ns = 20 ps


#### 6.Identify issues in the DRC section of the old Magic tech file for the SkyWater process and resolve them.

#### Link to Sky130 Periphery rules:- (https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html)

#### Commands to download and view the corrupted SkyWater process Magic tech file and its associated files for DRC corrections.
```
//go to home directory
cd

//Command to download the lab files
wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz

//command to extract file
tar xfz drc_tests.tgz

// change directory to lab folder
cd drc_tests

//List all files and directories present in the current directory
ls -al

//Command to view .magicrc file
gvim .magicrc

//Command to open magic tool in better graphics
magic -d XR &
```

![315554521-1b4cf68e-fa83-4d44-9b08-ca2b63ceb471](https://github.com/user-attachments/assets/b129f01e-98d3-4e95-b56f-a290ba931e46)

#### Magic file created
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/magic%20file%20created.png)

#### Open met3.mag file
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/met3_mag%20file%20opening.png)

#### Loading Poly
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/load%20poly.png)
![315561187-acfbcf69-020e-4b62-96bd-b7630aa74ef0](https://github.com/user-attachments/assets/bb8c07a6-ee92-4d5b-a209-224975a4b3d7)
![315578575-a05bd29a-b181-4e26-826a-d32f12696b2c](https://github.com/user-attachments/assets/54802cac-68ba-4b7c-8c7a-fb24a9ee655d)

### New commands have been added to the sky130A.tech file to update the DRC.

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/poly.9%20touching%20illegal%20because%20alldif.png)

commands to run in tkcon
```
//command to load updated tech file
tech load sky130A.tech

//Must re-run drc check to see updated drc error
drc check

//Selecting region displaying the new errors and getting the error messages
drc why
```

#### DRC error due to Geometric Construct
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/DRC%20errors%20as%20geometrical%20construct.png)

#### Tapped nwell
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/tapped%20nwell.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/check%20error.png)

#### Theory
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(100).png)
Clock Net Shielding
___
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(105).png)
an example of how the routing is done


## Section-4
#### Pre-layout timing analysis and importance of good clock tree

#### 1.Fix up small DRC errors and verify the design is ready to be inserted into our flow.
#### Commands to open the custom inverter
```
//changing directory
cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign

// load inverter in magic tool
magic -T sky130A.tech sky130_inv.mag &
```

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/dimension%20of%20grid.png)

Command to run in tkcon for setting grid and locali layer
```
# Syntax for grid command
help grid

# Set grid values accordingly
grid 0.46um 0.34um 0.23um 0.17um

```

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/grid%20formation.png)

#### 2.Save the finalized layout with a custom name and then open it.
 
 Command to save the layout with a custom name in the Tkcon window.
```
//Command to save as
save sky130_vsdinv.mag
```
Command to open the recently saved layout.
```
magic -T sky130A.tech sky130_vsdinv.mag &

```

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/port%20define%20and%20set%20value.png)

#### 3.Generating lef file from the layout
```
//command
lef write
```



![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/mag%20to%20lef%20file.png)


![316297206-15557990-33b4-4402-8c72-39b75da9ed07](https://github.com/user-attachments/assets/af419841-1daf-4aea-a729-cde4732c32f7)

#### 4.Copy the new lef file to src directory
```
//Copy lef file
cp sky130_vsdinv.lef ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

copy lib files
cp libs/sky130_fd_sc_hd__* ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

// you can check whether files are being copied to the folder by running command
ls

```
![316298066-78559cee-ad3f-4301-83ae-df99f8417be3](https://github.com/user-attachments/assets/c15660df-1737-4f99-bbb5-8f2c7dbd2765)

#### 5.Edit config.tcl to update the library file and incorporate the new LEF into the OpenLane flow

Commands to be added to config.tcl file

```
set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]
```
Edited config.tcl to include the added lef and change library to ones we added in src directory

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/config_tcl%20setup.png)


#### 6.To run openlane flow with newly added custom inverter cell

```
# Open openlane flow directory in new terminal
cd Desktop/work/tools/openlane_working_dir/openlane

# alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
# Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
```

```
to invoke the OpenLANE flow in the Interactive mode 
./flow.tcl -interactive

//command for packages need for openlane
package require openlane 0.9

//preparing the design for picorv32a
prep -design picorv32a

//Adiitional commands to include newly added lef to openlane flow
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

command to run synthesis
run_synthesis
```

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/lef%20to%20openflow.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/synthesis%20done.png)

#### 7.Mitigate or eliminate the newly introduced violations caused by the custom inverter cell by adjusting the design parameters.

Commands to view and change parameters to improve timing and run synthesis

```
//prep design again to update variables
prep -design picorv32a -tag 11-10_06-41 -overwrite

//Addiitional commands to include newly added lef to openlane flow merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

//Command to display current value of variable SYNTH_STRATEGY
echo $::env(SYNTH_STRATEGY)

//Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

//Command to display current value of variable SYNTH_BUFFERING to check whether it's enabled
echo $::env(SYNTH_BUFFERING)

//Command to display current value of variable SYNTH_SIZING
echo $::env(SYNTH_SIZING)

//Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

//Command to display current value of variable SYNTH_DRIVING_CELL to check whether it's the proper cell or not
echo $::env(SYNTH_DRIVING_CELL)

//Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/setting%20up%20corrected%20values.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/synthesis%20successfull%20with%200%20tnsand%200%20wns.png)

#### 8.Once synthesis has accepted our custom inverter, we can proceed with the floorplan and placement, and verify that the cell is integrated into the PnR flow.
```
//now run floorplan
run floorplan
```

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/error%20for%20floorplan.png)
```
//Since we are getting error in  running floorplan , we can use below commands to fix it
init_floorplan
place_io
tap_decap_or
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/commands%20to%20be%20run%20for%20error%20in%20floorplan.png)
```
//once errors are fixed , go for placement
run_placement
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/placement%20done.png)

Commands to load placement def in magic in another terminal

```
//change directory to generated placement file ....
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/11-10_06-41/results/placement/

```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/def%20file%20in%20placement.png)
```
//command to load placement def file in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/magic%20layout.png)
```
command to see internal connectivity layers
expand
```

The power pins are visibly abutted against other cells in the library

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/custom%20cell%20vsdnav%20with%20expand%20command.png)

#### 9.Perform post-synthesis timing analysis using the OpenSTA tool.

Since we have 0 WNS after the improved timing run, we will conduct timing analysis on the initial synthesis run, which has numerous violations and no parameters added for timing improvement.

```
//Change directory to openlane flow directory
cd Desktop/work/tools/openlane_working_dir/openlane

//alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
//Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
```

```
to invoke the OpenLANE flow in the Interactive mode 
./flow.tcl -interactive

//command for packages need for openlane
package require openlane 0.9

//preparing the design for picorv32a
prep -design picorv32a

//Adiitional commands to include newly added lef to openlane flow
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

//set new value tfor synth size
set ::env(SYNTH_SIZING) 1

command to run synthesis
run_synthesis
```

Screenshots for command that are running

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/to%20create%20pre%20sta%20file.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/merged_lef%20file.png)

A newly created my_base.sdc file for STA analysis is located in the openlane/designs/picorv32a/src directory, based on the openlane/scripts/base.sdc file.

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/vim%20my%20base%20sdc%20file.png)

A newly created `pre_sta.conf` file for STA analysis is located in the OpenLane directory.

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/vim%20pre%20sta%20file.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/1st%20slack.png)

Since increased fanout is causing additional delay, we can add parameters to reduce fanout and perform synthesis again.

```
//prep the design again 
prep -design picorv32a -tag 11-10_06-41 -overwrite

//include newly added lef to openlane flow
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

//set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

//set new value for SYNTH_MAX_FANOUT
set ::env(SYNTH_MAX_FANOUT) 4

//display current value of variable SYNTH_DRIVING_CELL
echo $::env(SYNTH_DRIVING_CELL)

//design is prepped and ready, we can run synthesis using following command
run_synthesis
```

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/giving%20max%20fanout%20is%204.png)

Command to run STA in other terminal
```
//Change directory to openlane
cd Desktop/work/tools/openlane_working_dir/openlane

//Command to invoke OpenSTA tool with script
sta pre_sta.conf
```

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/after%20synthesis%20sta%20run.png)

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/or%20taking%204%20fanouts.png)

#### 10.Make timing ECO fixes to remove all violations.
 
  OR gate of drive strength 2 is driving 4 fanouts
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/optimising%20time%20by%20reducing%20drive%20strength.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%20reduced.png)

Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4
```
//Reports all the connections to a net
report_net -connections _11675_

//Replacing cell
replace_cell _14514_ sky130_fd_sc_hd__or3_4

//Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%202nd%20reduction.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%202nd%20reduction%20result.png)
```
//Reports all the connections to a net
report_net -connections _11675_

//Replacing cell
replace_cell _14514_ sky130_fd_sc_hd__or3_4

//Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%203rd%20reduction.png)

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%203rd%20reduction%20result.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%204th%20reduction.png)

Result Slack is reduced

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%204th%20reduction%20result.png)

Commands to verify instance _14506_ is replaced with sky130_fd_sc_hd__or4_4
```
# Generating custom timing report
report_checks -from _29043_ -to _30440_ -through _14506_
```
#### Screenshot of replaced instance
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/14506%20is%20replaced%20by%20fc_sd_hd.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/4th%20slack%20reduction%20result.png)
We started ECO fixes at wns -23.9000 and now we stand at wns -22.6173 we reduced around 1.2827 ns of violation

#### 11.Replace the old netlist with the new netlist generated after the timing ECO fix, and then implement the floorplan, placement, and clock tree synthesis (CTS).

Now, to incorporate this updated netlist into the PnR flow, we can use write_verilog to overwrite the synthesis netlist. However, before doing so, we will create a copy of the old netlist.

copying the netlist
```
# Change directory to synthesis results directory
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/25-03_18-52/results/synthesis/

# Copy and rename the netlist
cp picorv32a.synthesis.v picorv32a.synthesis_old.v

# List contents of the directory
ls
```
commands for writing verilog
```
# Check syntax
help write_verilog

# Overwriting current synthesis netlist
write_verilog /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/25-03_18-52/results/synthesis/picorv32a.synthesis.v

# Exit from OpenSTA since timing analysis is done
exit
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/write%20verilog%20.png)

Commands to load the design and run necessary stages
```
//Now once again we have to prep design so as to update variables
prep -design picorv32a -tag 11-10_06-41 -overwrite

//Addiitional commands to include newly added lef to openlane flow merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

//Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

//Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

//Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

//Follwing commands are alltogather sourced in "run_floorplan" command
init_floorplan
place_io
tap_decap_or

//Now we are ready to run placement
run_placement

//Incase getting error
unset ::env(LIB_CTS)

//With placement done we are now ready to run CTS
run_cts
```

#### Changing The netlist
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/changing%20netlist.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/overwrite.png)

run_synthesis succesful
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/run%20synthesis%20succesful.png)

#### Floorplan Complete
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/floorplan%20complete.png)

#### Placement Complete
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/run%20placement%20complete.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/run%20cts.png)
#### Run_Cts succesfull
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/successful%20run%20of%20cts.png)

#### 12. Post-CTS OpenROAD timing analysis.

Commands to be run in OpenLANE flow to do OpenROAD timing analysis with integrated OpenSTA in OpenROAD


```
//run OpenROAD tool
openroad

//Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/24-03_10-03/tmp/merged.lef

//Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/cts/picorv32a.cts.def

//Creating an OpenROAD database to work with
write_db pico_cts.db

//Loading the created database in OpenROAD
read_db pico_cts.db

//Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/synthesis/picorv32a.synthesis_cts.v

//Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

//Link design and library
link_design picorv32a

//Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

//Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

//Check syntax of 'report_checks' command
help report_checks

//Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

//Exit to OpenLANE flow
exit
```
### Screenshots of commands run and timing report generated

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/post%20cts%20run.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/post%20cts%20run%20successful.png)


#### 13.Explore post-CTS OpenROAD timing analysis by removing 'sky130_fd_sc_hd__clkbuf_1' cell from clock buffer list variable 'CTS_CLK_BUFFER_LIST'.

Commands to be run in OpenLANE flow to do OpenROAD timing analysis after changing CTS_CLK_BUFFER_LIST

```
//Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

//Removing 'sky130_fd_sc_hd__clkbuf_1' from the list
set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0]

//Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

//Checking current value of 'CURRENT_DEF'
echo $::env(CURRENT_DEF)

//Setting def as placement def
set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/placement/picorv32a.placement.def

//Run CTS again
run_cts

//Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

//Command to run OpenROAD tool
openroad

//Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/24-03_10-03/tmp/merged.lef

//Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/cts/picorv32a.cts.def

//Creating an OpenROAD database to work with
write_db pico_cts1.db

//Loading the created database in OpenROAD
read_db pico_cts.db

//Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/synthesis/picorv32a.synthesis_cts.v

//Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

//Link design and library
link_design picorv32a

//Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

//Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

//Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

//Report hold skew
report_clock_skew -hold

//Report setup skew
report_clock_skew -setup

//Exit to OpenLANE flow
exit

//Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

//Inserting 'sky130_fd_sc_hd__clkbuf_1' to first index of list
set ::env(CTS_CLK_BUFFER_LIST) [linsert $::env(CTS_CLK_BUFFER_LIST) 0 sky130_fd_sc_hd__clkbuf_1]

//Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)
```


![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/open%20road%20with%20cts%20run.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/run%20of%20open%20road.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/post%20cts%20road%20setup.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/run%20cts%20again.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/cts%20run%20complete.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/openroad%20setup%20after%20cts%20run%20for%202nd%20time.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/report%20of%20setup%20and%20hold%20skew.png)



#### Theory
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(111).png)
Pre Processed route Guides
___


## Section-5

#### 1.Perform generation of Power Distribution Network (PDN) and explore the PDN layout.
Commands to perform all necessary stages up until now

```
//Change directory to openlane flow directory
cd Desktop/work/tools/openlane_working_dir/openlane

//alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
//Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
```

```
to invoke the OpenLANE flow in the Interactive mode 
./flow.tcl -interactive

//command for packages need for openlane
package require openlane 0.9

//preparing the design for picorv32a
prep -design picorv32a

//Adiitional commands to include newly added lef to openlane flow
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

//set new value tfor synth size
set ::env(SYNTH_SIZING) 1

command to run synthesis
run_synthesis

# Following commands are alltogather sourced in "run_floorplan" command
init_floorplan
place_io
tap_decap_or

# Now we are ready to run placement
run_placement

# Incase getting error
unset ::env(LIB_CTS)

# With placement done we are now ready to run CTS
run_cts

# Now that CTS is done we can do power distribution network
gen_pdn 
```

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/run%20gen%20pdn.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/successful%20run%20of%20gen%20pdn.png)

Commands to load PDN def in magic in another terminal

```
# Change directory to path containing generated PDN def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/12-10_16-14/tmp/floorplan/

# Command to load the PDN def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read 14-pdn.def &
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/screenshot%20of%20pdn%20def.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/magiclayout%20triton.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/magic%20layout%202.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/magic%20layout%203.png)

#### 2.Perfrom detailed routing using TritonRoute and explore the routed layout.
commands for performing Routing
```
# Check value of 'CURRENT_DEF'
echo $::env(CURRENT_DEF)

# Check value of 'ROUTING_STRATEGY'
echo $::env(ROUTING_STRATEGY)

# Command for detailed route using TritonRoute
run_routing
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/run%20routing%20completed.png)

#### 3.Commands to load routed def in magic in other terminal
```
# Change directory to path containing routed def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/12-10_16-14/results/routing/

# Command to load the routed def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.def &
```

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/routed%20layout%201.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/routed%20layout%202.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/routing%20layout%203.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/routing%20layout%204.png)

#### 4.Post-Route OpenSTA timing analysis with the extracted parasitics of the route.
```
# Command to run OpenROAD tool
openroad

# Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/12-10_16-14/tmp/merged.lef

# Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/12-10_16-14/results/routing/picorv32a.def

# Creating an OpenROAD database to work with
write_db pico_route.db

# Loading the created database in OpenROAD
read_db pico_route.db

# Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/12-10_16-14/results/synthesis/picorv32a.synthesis_preroute.v

# Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

# Link design and library
link_design picorv32a

# Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

# Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

# Read SPEF
read_spef /openLANE_flow/designs/picorv32a/runs/12-10_16-14/results/routing/picorv32a.spef

# Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

# Exit to OpenLANE flow
exit
```

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/post%20route%20openroad.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/open%20sta%20timing%20analysis.png)






















































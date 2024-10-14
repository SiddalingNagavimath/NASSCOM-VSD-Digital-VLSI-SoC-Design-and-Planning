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
### DAY_1
![core and die](https://github.com/user-attachments/assets/2ca224f5-e409-45c3-89be-0999db08200a)
![Screenshot](https://github.com/user-attachments/assets/8ab89589-2d39-43d7-b621-51d70e265a73)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/rtl%20to%20gds%20flow.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(42).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(43).png)


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
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/VirtualBox_vsdworkshop_08_10_2024_23_56_32.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/run_synthesis%20complete.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/yosus%204%20synthesis%20report.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/VirtualBox_vsdworkshop_08_10_2024_23_58_23.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/VirtualBox_vsdworkshop_09_10_2024_00_01_18.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/cell_level%20lef%20info.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/pdk%20used%20by%20run%20etc.png)

## Calculating Flop_Ratio(D_flipflop):-  
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/dff%20flop%20ratio.png)
![core and die](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_1/dff%20flop%20ratio%20ans.png)                     

**total no.of cells**=14876                                                                 
**no.of d_ff**=1613                                                                     
**flop_ratio**=(1613/14876)=0.1084296853993009                                        
**Percentage**= flop_ratio*100=10.84296853993009%







### DAY_2
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(48).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(49).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(51).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(53).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(54).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(55).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(57).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/incre_or_decree%20in%20size%20of%20ioplacecell.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/Global%26local%20variable%20in%20readme.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/core%20utl%20overriden%20by%20pdk%20specific%20configtcl.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/def%20file%20of%20floorplan.png)

### Floorplan Def file gives the values of ..                                                  
Die width in units=660685/1000=660.685 (in microns)                                           
Die height in units=671405/1000=671.405                                                       
//let's find the Area                                                   
Area of Die = 660.685*671.405 = 443587.212425 square microns

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/floorplan%20variable.png)

```
//Change directory to newly generated floorplan def file
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/11-10_06-41/results/floorplan/

// command to run floorlan def file in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/Magic%20opening.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/magic%20placement.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/magic_io_metal.png)






### DAY_3

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/op%20of%20size%20ioplace.png)
```
//Command to run in openlane working flow
run_placement
```
```
// change directory to newly generated placement file in another terminal
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/11-10_06-41/results/placement/

// command to run placement def fie in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

```
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/placement%20def%20in%20magic.png)
```
command to exit in the openflow
exit
exit
```
Cloning the custom inverter standard cell design from github repo
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


![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/layout%20for%20cmos%20inverter%20by%20git%20clone.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/location%20of%20n%26p%20mos%20in%20cmos.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/show%20what%20s%20layout%20and%20lef.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/ext2spice%20file%20creation.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/circuit%20for%20inv_ext%20file.jpeg)

#Spice extraction of inverter in Magic
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

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/ext%20and%20spice%20file%20create.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/gitclone.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/copied%20from%20magic%20(sky130a).png)

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(59).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(60).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(61).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(62).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(63).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(65).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(66).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(67).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(69).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(71).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(75).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(76).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(77).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(78).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(79).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(80).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(81).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(83).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(84).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(85).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(86).png)

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/ngspice%20input.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/values%20obtained%20from%20ngspice.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/output%20vs%20time%20in%20transition.png)

```
# Rise transition time calculation
Rise transition time = time taken for o/p to rise to 80% - time taken for i/p to rise to 20%
20% of output = 660mV 
80% of output = 2.64
```

# 20% Screenshots
![314002633-261c420f-219f-4c26-ae32-6c0db82a722e](https://github.com/user-attachments/assets/487b7b0c-c147-4e63-9720-319fe4f3d206)
![314004259-bbb078c4-b3aa-436b-8832-23e5d7777081](https://github.com/user-attachments/assets/50ad862b-3b5e-446d-b376-719415dc38a9)

# 80% Screenshots
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






![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/magic%20file%20created.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/met3_mag%20file%20opening.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/load%20poly.png)
![315561187-acfbcf69-020e-4b62-96bd-b7630aa74ef0](https://github.com/user-attachments/assets/bb8c07a6-ee92-4d5b-a209-224975a4b3d7)
![315578575-a05bd29a-b181-4e26-826a-d32f12696b2c](https://github.com/user-attachments/assets/54802cac-68ba-4b7c-8c7a-fb24a9ee655d)

commands to run in tkcon
```
# command to load updated tech file
tech load sky130A.tech

# Must re-run drc check to see updated drc error
drc check

# Selecting region displaying the new errors and getting the error messages
drc why
```










![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/poly.9%20touching%20illegal%20because%20alldif.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/poly%20resistor%20spacing%20to%20diff%20nd%20tap.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/DRC%20errors%20as%20geometrical%20construct.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/tapped%20nwell.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/check%20error.png)

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(87).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(88).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(89).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(90).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(91).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(92).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(93).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(94).png)





### DAY_4
Commands to open the custm inverter
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
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/port%20define%20and%20set%20value.png)

## Generating lef file from the layout
```
//command
lef write
```



![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/mag%20to%20lef%20file.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/config_tcl%20setup.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/lef%20to%20openflow.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/synthesis%20done.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/setting%20up%20corrected%20values.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/synthesis%20successfull%20with%200%20tnsand%200%20wns.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/error%20for%20floorplan.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/commands%20to%20be%20run%20for%20error%20in%20floorplan.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/placement%20done.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/def%20file%20in%20placement.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/magic%20layout.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/custom%20cell%20vsdnav%20with%20expand%20command.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/to%20create%20pre%20sta%20file.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/merged_lef%20file.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/vim%20my%20base%20sdc%20file.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/vim%20pre%20sta%20file.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/1st%20slack.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/giving%20max%20fanout%20is%204.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/after%20synthesis%20sta%20run.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/or%20taking%204%20fanouts.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/optimising%20time%20by%20reducing%20drive%20strength.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%20reduced.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%202nd%20reduction.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%202nd%20reduction%20result.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%203rd%20reduction.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%203rd%20reduction%20result.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%204th%20reduction.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/slack%204th%20reduction%20result.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/14506%20is%20replaced%20by%20fc_sd_hd.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/4th%20slack%20reduction%20result.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/changing%20netlist.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/overwrite.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/run%20synthesis%20succesful.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/floorplan%20complete.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/run%20placement%20complete.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/run%20cts.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(95).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(96).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(97).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(98).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(99).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(100).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(101).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(102).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(103).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(104).png)

### DAY_5
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(105).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(106).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(107).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(108).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(109).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(110).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(111).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(112).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(113).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(114).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(115).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Concept_Corner/Screenshot%20(116).png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/successful%20run%20of%20cts.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/post%20cts%20run.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/post%20cts%20run%20successful.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/open%20road%20with%20cts%20run.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/run%20of%20open%20road.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/post%20cts%20road%20setup.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/run%20cts%20again.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/cts%20run%20complete.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/openroad%20setup%20after%20cts%20run%20for%202nd%20time.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/report%20of%20setup%20and%20hold%20skew.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/run%20gen%20pdn.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/successful%20run%20of%20gen%20pdn.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/screenshot%20of%20pdn%20def.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/magiclayout%20triton.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/magic%20layout%202.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/magic%20layout%203.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/run%20routing%20completed.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/routed%20layout%201.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/routed%20layout%202.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/routing%20layout%203.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/routing%20layout%204.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/post%20route%20openroad.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_5/open%20sta%20timing%20analysis.png)






















































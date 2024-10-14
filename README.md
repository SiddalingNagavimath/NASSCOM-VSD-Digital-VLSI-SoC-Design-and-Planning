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
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/Global%26local%20variable%20in%20readme.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/core%20utl%20overriden%20by%20pdk%20specific%20configtcl.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/def%20file%20of%20floorplan.png)

### Floorplan Def file gives the values of ..                                                  
Die width in Distance=660685-0=660685                                                         
Die height in Distance=671405-0=671405

![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/floorplan%20variable.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/Magic%20opening.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/magic%20placement.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_2/magic_io_metal.png)






### DAY_3
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/incre_or_decree%20in%20size%20of%20ioplacecell.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/op%20of%20size%20ioplace.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/layout%20for%20cmos%20inverter%20by%20git%20clone.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/location%20of%20n%26p%20mos%20in%20cmos.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/show%20what%20s%20layout%20and%20lef.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/ext2spice%20file%20creation.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/circuit%20for%20inv_ext%20file.jpeg)
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
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/magic%20file%20created.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/met3_mag%20file%20opening.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_3/load%20poly.png)
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
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/dimension%20of%20grid.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/grid%20formation.png)
![Screenshot](https://github.com/SiddalingNagavimath/NASSCOM-VSD-Digital-VLSI-SoC-Design-and-Planning/blob/main/Lab_works/Day_4/port%20define%20and%20set%20value.png)
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






















































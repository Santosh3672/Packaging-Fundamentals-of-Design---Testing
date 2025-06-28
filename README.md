# Packaging Fundamentals of Design and Testing 20-29 June 2025
VSD Workshop on Packaging fundamentals on design and testing with labs based on Ansys 20-29June 2025

## Contents
### [Packaging Evolution: From Basics to 3D Integration:](#head1_1)
#### [Introduction to Packaging and its Requirement](#head1_2)
#### [Components of Package and its significance in semiconductor cycle](#head1_3)
#### [Overview of different types of Packaging technologies](#head1_4)
#### [Comparative analysis and selecting the righ Package type](#head1_5)

### [Wafer to Package: Assembly and Manufacturing Essentials](#head2_1)
#### [Packaging and Manifacturing Terminologies](#head2_2)
#### [Steps Involved in manufacturing a Wire Bond package](#head2_3)
#### [Steps Involved in manufacturing a Flip chip package](#head2_4)
#### [Steps Involved in manufacturing a Wafer layer package](#head2_5)

### [Lab1: Thermal Analysis of Package using Icepak](#head3_1)
#### [Introduction to Ansys tool](#head3_2)
#### [Instantiating prebuilt Package for Thermal Analysis](#head3_3)
#### [Defining Boundary condition and Adding Monitors](#head3_4)
#### [Mesh generation for analysis and Viewing Results](#head3_5)

###  [Introcudtion to Package testing](#head4_1)
#### [AOST: Assembly Open and Short Test](#head4_2)
#### [Burn-in Test](#head4_3)
#### [Final test and ATE](#head4_4)

### [Lab2: Building a Semiconductor Package from Scratch](#head5_1)
#### [Die, Substrate and Die attach creation](#head5_2)
#### [Die bondpad, Substrate bondpad and Wire bonding creation](#head5_3)
#### [Wire bonding for whole design](#head5_4)
#### [Mold addition](#head5_5)

### [Acknowledgement](#head6)
## <a name="head1_1"></a>Packaging Evolution: From Basics to 3D Integration:
### <a name="head1_2"></a>Introduction to Packaging and its Requirement
Packaging is the process of transforming bare semiconductor dies—fabricated on silicon wafers—into robust, functional components that can be mounted onto printed circuit boards (PCBs). It serves as a critical bridge between the microscopic world of silicon and the macroscopic realities of real-world electronics.

Need for Semiconductor Packaging
1. **Die Protection**: Safeguards the fragile semiconductor die from:
   - Corrosive environments  
   - Moisture ingress  
   - Mechanical shock  
   - Handling-related damage  
   
   This ensures the long-term reliability of the device.

2. **Electrical Interconnectivity**:  Enables electrical connection of the die to external circuitry such as:
   - Printed Circuit Boards (PCBs)  
   - Other dies in multi-die systems (advanced configurations)  
   
Techniques used include:
   - Wire bonding  
   - Flip-chip  

### <a name="head1_3"></a>Components of Package and its significance in semiconductor cycle

A semiconductor packages contain following elements:

**Molding Compound** – An epoxy-based resin that encapsulates the die and wire bonds, offering mechanical protection and shielding against moisture, dust, and contaminants. 

**Substrate** – A crucial interposer that bridges the silicon die and the PCB. It contains metal traces and vias for electrical routing, and provides mechanical stability. 

**Die Attach** – Usually a thermally conductive adhesive or solder material that secures the die onto the substrate, enabling heat dissipation and mechanical anchoring. 

**Wire Bond** – Typically made of gold, copper, or aluminum, these fine wires connect the bond pads on the die to the corresponding pads on the substrate. 

**Traces** – Embedded metal lines within the substrate that carry electrical signals between the wire bonds and the external interface of the package. 

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_a2.png)
*Fig: Components a wire bond BGA package*


Once silicon wafers are manufactured, individual dies are separated, packaged, and rigorously tested. This step prepares the chips for real-world integration by enabling thermal management, mechanical protection, and secure electrical interfacing with PCBs.

**Fabless companies:** These companies focus solely on chip architecture, RTL development, physical design, and verification. Upon finalizing the design, they deliver the GDSII file to a semiconductor foundry for fabrication. They do not own wafer fabs or engage in packaging/test. 

**Outsourced Semiconductor Assembly and Test (OSAT):** OSATs provide third-party services to fabless and IDM companies, handling wafer probing, die packaging (e.g., wire bond, flip-chip, fan-out), final testing, and delivery. 

**Integrated Device Manufacturer(IDM):** IDMs own and manage the complete silicon lifecycle—from design to fabrication and packaging/testing. This vertically integrated model gives them more control over costs, timelines, and supply chain resilience. 

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_a3.png)
*Fig: Packaging & testing in Semiconductor flow*


**Key Factors in Selecting the Right Semiconductor Package**:

   1. **I/O Requirements (Pin Count)**: The number and density of input/output connections determine whether to use high-density packages (e.g., BGA, CSP) or simpler ones (e.g., QFP, SOIC). 

   2. **Thermal Performance**: Packages must dissipate heat effectively to maintain device reliability. Materials like ceramics or metal-core substrates are preferred for high-power applications. 

   3. **Form Factor and Footprint**: The package size must align with the PCB layout and available space—especially critical in portable and miniaturized devices. 

   4. **Reliability and Mechanical Durability**: Influenced by environmental conditions and material choices—packages must withstand thermal cycling, vibration, moisture, and handling stress. 

   5. **Cost and Production Volume**: There's a trade-off between performance and cost. Simpler packages may be cost-effective for high-volume products, while advanced ones (e.g., flip-chip, fan-out) suit high-performance designs despite higher expense. 

   6. **End Application Requirements**: Automotive, aerospace, and medical devices may demand high-reliability packages with long lifespans, while consumer electronics may favor compact, cost-optimized options. 


![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_a6.png)
*Fig: Visual representation of the integration of Chip, Package and board*

Carrier: Substrate at packaging level

Die-to-carrier interconnect: Die attach

### <a name="head1_4"></a>Overview of different types of Packaging technologies


**1. Through-Hole Mounting (THM)**

Packages with long pins that pass through holes on the PCB—ideal for prototyping and robust mechanical anchoring.

   - **DIP (Dual In-line Package)**: Two parallel rows of pins; commonly used in ICs for prototyping. 

   - **SIP (Single In-line Package)**: Pins arranged in a single row; used in resistor networks or small logic devices. 

   - **TO (Transistor Outline)**: Metal-can style for discrete transistors and power devices with excellent heat dissipation. 

   - **PGA (Pin Grid Array)**: Grid-style pin layout offering higher I/O density than DIP/SIP—used in CPUs and high-pin-count devices. 


**2. Surface Mount Technology (SMT)**

Packages designed for direct mounting on PCB surfaces—key to miniaturization and automated assembly.

   - **QFN (Quad Flat No-lead)**: Exposed thermal pad underneath; compact with excellent thermal/electrical performance. 

   - **QFP (Quad Flat Package)**: Gull-wing leads on all four sides; used for microcontrollers and ASICs. 

   - **PBGA (Plastic Ball Grid Array)**: Solder balls arranged in a grid; provides high I/O density and better thermal management. 

   - **LGA (Land Grid Array)**: Similar to BGA, but uses flat contacts instead of balls; improves electrical performance. 

   - **CSP (Chip Scale Package)**: Extremely compact—package size nearly matches die size; ideal for mobile and wearables. 

   - **PoP (Package on Package)**: Vertical stacking of packages (e.g., logic + memory); space-saving for high-functionality systems. 

   - **MCM (Multi-Chip Module)**: Multiple dies integrated in a single package for high performance and integration. 

   - **CoWoS (Chip-on-Wafer-on-Substrate)**: An advanced 2.5D packaging method enabling high-bandwidth interconnect between dies; used in high-end SoCs and AI accelerators.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_a7.png)
*Fig: Popular packaing techniques (TMM and SMT)*


**3.Advanced package substrate**:

For multiple die in a package we can also add layers between die and substrate:

   - **2D**: Two dies are connected to substrate and are connected at ball-grid level, there is a longer connection between two dies but it is better than two separate packages.

   - **2.1D**: A Redistribution layer (RDL) is put between Dies and substrate which is faster than 2D.

   - **2.3D**: An organic interposer that has multiple layers is used between die and substrate. Multiple layers of interposer is helpful when there is high IO density.

   - **2.5D**: Silicon interposer is used between die and substrate.

   - **3D**: Chip is put on top of another chip.


![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_a9.png)
*Fig: Cross sectional view of different packaging techniques*


**Option for carrier**: Leadframe(DIP, QFN) . Laminate(multiple layers) , plastic, ceramic (high temp.), organic RDL, silicon, glass

Options for interconnections: 

   - **Wirebond**: stiching interconnects

   - **Bump/solder**: Connecting the die and substrate directly through bump/solder


![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_a10.png)
*Fig: Chip to board connections for different packages*


### <a name="head1_5"></a>Comparative analysis and selecting the righ Package type

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_a11.png)
*Fig: Compararision between different packaging techniques*

Packages left end like DIP,  QFN are low cost and easy to assemble, but they occupy large space and as we move towards the right they become compact with more IO density and are suitable for high performance, but their cost increases.


## <a name="head2_1"></a>Wafer to Package: Assembly and Manufacturing Essentials
### <a name="head2_2"></a>Packaging and Manufacturing Terminologies
1. **ATMP (Assembly, Testing, Marking, and Packaging):**
A critical post-fabrication stage encompassing:
    - Assembly of the die into its package 
    - Electrical testing to screen functional and defective parts 
    - Marking for traceability (e.g., logo, lot ID, part number) 
    - Packaging to protect the die and establish I/O interfaces 
2. **Manufacturing Organizations:**
    - In-House Facilities:
Large IDMs like Intel, Samsung, and SK Hynix manage ATMP within their ecosystem, ensuring tight control over IP, quality, and supply chain logistics. 
    - OSAT (Outsourced Semiconductor Assembly and Test):
Specialized third-party providers like ASE Group, Amkor, and increasingly Tata Electronics offer scalable ATMP services to fabless companies and IDMs alike. 
3. **Clean Room Environments:**
Semiconductor packaging and testing are performed in highly controlled clean room environments to minimize particle contamination.
    - Class Ratings (e.g., Class 1000): Indicate max allowable particles per cubic foot of air. 
    - ISO Standards (e.g., ISO 6): International benchmarks for air cleanliness.
These cleanrooms often occupy the largest footprint in ATMP facilities and are critical for ensuring process integrity during wire bonding, mold encapsulation, and optical inspections. 

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_b1.png)
*Fig: ATMP plant in semiconductor supply chain*



**Sections of an ATMP unit**
 - **Testing Area:** Final packaged devices undergo rigorous electrical characterization, thermal performance evaluation, and reliability stress testing (e.g., burn-in, thermal cycling, ESD testing). This ensures that only functional and robust units proceed to shipment. 

 - **Material Preparation & Storage:** Houses various raw materials required for assembly—such as lead frames, substrates, mold compounds, bonding wires, and adhesives. Environmental controls are often in place to preserve material integrity. 

 - **Utility & Maintenance Infrastructure:** Supports continuous manufacturing through stable power, pure water, compressed air, vacuum systems, and regular equipment calibration and maintenance. Critical for yield consistency and process safety. 

 - **Warehouse (Finished Goods Storage):** Stores final packaged and tested devices under controlled conditions until dispatch. Includes automated inventory tracking and quality audit zones to ensure compliance and traceability. 

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_b2.png)
*Fig: Representative ATMP unit layout*

**Activities inside Wafer Preparation Area (clean room):**
  1. **Wafer Carrier Reception:** Wafers fabricated at the foundry are transported in protective carriers designed to prevent mechanical damage, contamination, and static discharge. 
  2. **Wafer Inspection:** Upon arrival, wafers undergo visual and metrology-based inspection to identify physical defects, alignment issues, or contamination. Defective wafers are rejected before proceeding. 
  3. **Wafer Front-Side Tape Lamination:** A protective tape is laminated onto the front (device) side of the wafer to shield delicate circuit elements during back grinding and dicing. 
  4. **Wafer Backside Grinding:** The non-active backside of the wafer, which often includes additional supporting materials, is ground down to achieve the target thickness suitable for packaging. This step enhances thermal performance and minimizes z-height. 
  5. **Tape Frame Mounting:** After grinding, the wafer becomes mechanically fragile. To enable safe handling during dicing, it is mounted onto a tape frame, which provides structural support. 
  6. **Wafer Dicing:** The wafer is singulated into individual dies through a two-step process: 
   - **Laser Grooving:** Pre-cuts shallow trenches to weaken die streets. 
   - **Blade Dicing:** A high-speed diamond blade completes the separation with high precision. 

[Video on Wafer preparation](https://www.youtube.com/watch?v=hR5orrmpoeE&pp=ygUUYSBsb29rIGluc2lkZSBhbWtvciA%3D)

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_b3.png)
*Fig: Wafer preparation flow*

### <a name="head2_3"></a>Steps Involved in manufacturing a Wire Bond package
**Die Attach:** The individual die is mounted onto the substrate or leadframe using a thermally and mechanically conductive adhesive (e.g., epoxy, solder, or sintered silver). The pattern and uniformity of die attach directly influence thermal dissipation, mechanical stability, and long-term reliability. 

[Video on Die attach](https://www.youtube.com/watch?v=jliiUV0vDic&pp=ygUTRGllIGF0dGFjaCBvdmVydmlldw%3D%3D)

**Curing:** The adhesive is cured to strengthen the die-to-substrate bond. This is typically done using thermal ovens or UV curing systems, depending on the adhesive type. Proper curing ensures mechanical integrity and minimizes voids or delamination. 

**Wire Bonding (Stitching):** Fine wires (gold, copper, or aluminum) are bonded between the die pads and substrate pads using thermosonic wedge or ball bonding. Equipment like the HB100 automatic wire bonder enables precise, repeatable bonding with pattern recognition and loop profiling.

[Video on Stiching](https://www.youtube.com/watch?v=3YkGrhvrWxA&pp=ygUPaGIxMDAgYXV0b21hdGlj0gcJCb4JAYcqIYzv)

**Molding:** A mold compound (usually epoxy-based) is dispensed and cured to encapsulate the die and wire bonds. This provides mechanical protection, moisture resistance, and electrical insulation. 

**Marking:** The top surface of the molded package is laser-marked or ink-printed with identifiers such as part number, lot code, and manufacturer logo for traceability and quality control. 

**Singulation:** The molded panel is diced into individual packages using high-precision saws. This step isolates each unit for final testing and shipment. 

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_b4.png)
*Fig: Wire bond package manufacture flow*


### <a name="head2_4"></a>Steps Involved in manufacturing a Flip chip package

**Bump formation on Die:** This is an additional process where the solder bump is formed on the silicon through various steps which increases cost and complexity of flip chip. 
It involves following steps: 
- Formation of dielectric pattern creating sites for the fanout of die,
- Addition of under bump metalization(UBM) and bump solder at fanout location
- Reflow process is done where we put the die at high temperature.
 
**Fluxing Dispensing:** Bond pads are the point of contact for bumps in the substrate, to protect them from oxidation a protective flux coating is added. 

**Connecting Die and Substrate:** Bumped Die is flipped and aligning the bond pads and pressed. Then it is heated to join bumps and bond pad using a thermal compression process. Then the remaining flux is cleansed as it is not required.

**Underfill Dispensing:** An underfill is added between substrate to absorb the pressure due to thermal expansion coefficient between die and substrate. To increase its strength it is heated by curing.

**Molding**, **Marking** and **Ball formation** are same as that in wire bond process

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_b5.png)
*Fig: Flip chip package manufacture flow*

### <a name="head2_5"></a>Steps Involved in manufacturing a Wafer layer package

Wafer-Level Packaging (WLP) enables direct interconnection between the die and solder balls through Redistribution Layers (RDLs), eliminating the need for a traditional substrate. This approach supports compact form factors, enhanced electrical performance, and lower parasitics, making it ideal for high-speed applications. WLP manufacturing involves following disctinct steps:

**Reconstitution Process:** 
   - Known-good dies are inspected and placed on a temporary carrier with controlled spacing. 
   - A mold compound is applied to encapsulate the dies, forming a reconstituted wafer. 
   - The carrier is then released, leaving behind a planar molded wafer ready for further processing. 

**RDL Preparation:** 
  - The die to ball interconnection is prepared on a carrier by adding multiple layers of dielectric as insulator and metals for connection. 
  - Vias are patterned in the dielectric to connect metal layers, enabling complex routing. The number of RDL layers depends on the complexity of die fanouts. 
  - The RDL pattern is transferred to the reconstituted wafer and carrier is discarded. Then the Balls are formed on top RDL layer.
  - The RDL redistributes the die’s I/O pads to a larger area, allowing for ball pitch expansion (fan-out). 

**Package Singulation:** After ball formation the reconstituted wafer is diced to separate individual packages, each containing a die, RDL, and solder balls. 

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_b6.png)
*Fig: Wafer level packaging manufacture flow*

##  <a name="head3_1"></a> Lab1: Thermal Analysis of Package using Icepak
### <a name="head3_2"></a> Introduction to Ansys tool
Ansys Electronics Desktop(AEDT) is a comprehensive simulation suite used to design, analyze and optimize electronic systems across multiple physics domains.It is a unified platform that integrates tools such as:

   - **Ansys HFSS** – for high-frequency electromagnetic simulation (RF, microwave, antennas) 
   - **Ansys Maxwell** – for low-frequency electromagnetic and motor design 
   - **Ansys Q3D Extractor** – for parasitic extraction in 3D interconnects  
   - **Ansys Icepak** – for electronics thermal management using computational fluid dynamics

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_c1.png)
*Fig: Ansys Electronics desktop toolbar*

To get started with an analysis go to `tools->insert` icepak design or directly click `Icepak` icon from the toolbar, It will create a project with Icepak section.
Components in Icepak design analysis:

  - **3D components and model**
  - **Thermal:** Boundary condition
  - **Monitor:** Edges or points
  - **Mesh:** to solve the finite element analysis of bounding conditions
  - **Analysis:** solving the equation
  - **Results:** To view results of FEM


### <a name="head3_3"></a> Instantiating prebuilt Package for Thermal Analysis

To initiate prebuilt packages: Go to `Icepak -> Toolkit -> Geometry -> Packages` and select a required package.

Then we get an option to specify various parameters of the package as follows:

  - **Dimension:** Option to define the plane of package, Origin, Package dimensions, thickness and Symmetry
  - **Substrate:** Options to define Substrate layer, thickness, material, Configure traces and Vias
  - **Solder:** Define solder balls parameter like number of rows, columns and array type of balls and ball pitch, diameter, height etc.
  - **Die:** Define dimension of die, power dissipation, material, bump and heat sink information.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_c3.png)
*Fig: Parameters to be selected for a flipchip package instantiated from AEDT*

After selecting parameters of package click Ok and package will be formed which can be viewed in 3D viewer.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_c4.png)
*Fig: Pre built Flipchip package in AEDT 3D viewer*

On the left we have a model section where the individual elements of packages are mentioned.

Selecting a specific element highlights it in the 3D viewer.

### <a name="head3_4"></a> Defining Boundary condition and Adding Monitors
After package is created we can add boundary condition by selecting *die* or *traces* in `Thermal` section of the project manager then we can add power details in the Thermal Specification. 

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_c5.png)

*Fig: Thermal boundary condition applied to die source of 1W total power*

Similarly to assign thermal boundary condition to substrate, right click on substrate in Model section, then select `Assign thermal -> Source`. A similar pop-up will come where here we mention temperature as *Ambient temperature* to simulate outer world then press Finish to save the details.

To **monitor temperatures** in various sections of the package by adding monitors.

To add a monitor on an element right click on it then select `Assign monitor -> Point monitor` then select parameter say temperature for our case.

For our case we added monitor in die, underfill and substrate.

### <a name="head3_5"></a> Mesh generation for analysis and Viewing Results
In mesh generation is a process of dividing 3D model into small, discrete elements called as **Mesh**. To generate the mesh go to **simulation** section on top and select **generate mesh**, it will ask to save the file. 

After mesh is generated a mesh visualization pop-up comes, in that we can inspect the quality of mesh under quality section, where we can check parameters like face alignment and skewness of the mesh generated. A good quality mesh with low skewness and good face alignment resuots in an accurate simulation. 

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_c7.png)

*Fig: Mesh visialization*

For the **Analysis** on the Generated Mesh right click on Analysis and select `Add solution step` to configure the analysis. Select the required analysis type and save it by pressing ok it will create the analysis setting.


![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_c8.png)

*Fig: Configuration used for Icepak thermal analysis*

Before starting the analysis press validate in the simulation section, it will validate, design settings, 3D model, Boundary condition, Monitor, Mesh and Analysis setup.

Start analysis by pressing   `Analyse All` from the simulation section. Ensure there are no warnings during the analysis. After analysis is completed successfully following message will be shown on message manager:

<pre>```[info] Normal completion of simulation on server: Local Machine. (06:13:45 PM  Jun 26, 2025)```</pre>

To plot the result select full package by dragging and right click then select `plot field -> temperature -> Temperature`

Select the parameters requires, for our case surface plot is enabled, press done to start creating plot.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/picc13.png)

*Fig: Surface temperature plot of Flipchip package from different angles*

In our plot we see that die is at higher temperature due to 1W power dissipation that we selected and lack of heat sink in package. The substrate is at a lower temperature because we selected ambient temperature for it. 

From the plot we can identify regions with high temperature that could be of concern.

[Lab files](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Packaging_VSD_project_1.aedt)

##  <a name="head4_1"></a> Introcudtion to Package testing
During package testing the electrical, mechanical and thermal aspects of the manufactured Package are checked before using them in the board level.

Stages of testing:
  - Die level testing: Wafer probe test done at foundry or at OSAT during wafer preparation stage.
  - Package Testing: Testing the manufactured package for electrical, thermal and mechanical aspects.
  - System level Tests (SLT): Testing of all the packages in the system(board).

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_d1.png)

*Fig: Testing in various stages of semiconductor cycle*

At an ATMP the manufactured packages are loaded in a **package board** before sending them to testing area. 

There are three types of testing done on a package:
  - **Assembly open and short test (AOST):** Used to flag open or shorts created during packaging steps, ensures functional
  - **Burn-in:** Applying thermal and voltage stress to ensure early-life reliability
  - **Final test:** Testing the packages in cold and hot temperature temperature mentioned in the datasheet ensuring functionality over all scenarios.

### <a name="head4_2"></a> AOST: Assembly Open and Short Test
Objective: Quick test for shorts or opens on package leads or balls. Used to check functionality.
  - Testing immediately follows trim and form (lead frame packages) or singulation (BGA package).
  - Packages are put through an open/short test to screen for massive electrical falls before leaving assembly
  - There is also a visual inspection. Product grade sort (PGSRT) catches assembly related fails and sorts into product grade Best(1), Better(2), better(3), scrap(4).

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_d3.png)

*Fig: Example of failures detected in AOST tests*

Image above illustrates how open and shorts are formed due to bent shapes of die and substrate forming shorts like bridging nearby bumps and opens like Non wet open (NWO).
### <a name="head4_3"></a> Burn-in Test


A manufactured packages lifespan has 3 stage:
  - **Infant stage:** Just after its manufactured the package has high failure rate during initial stages due material defect, assembly error, etc. The failure rate drops gradually over time and usage.
  - **Useful Life:** This is where the risk related to early package failure are no longer present and the package has the lowest failure rate (due to random failure).
  - **Wear out:** After some time of operation the wear effect starts and failure rate increases, this is typical lifespan of the package.

The role of burn-in test is to accelerate the Infant Mortality stage and avoid any initial failure before using them on system level.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_d4.png)

*Fig: Burn-in test details*


### <a name="head4_4"></a> Final test and ATE
Final test is used to test the performance of package in the corner temperature that the product offers.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_d5.png)

*Fig: Final test details*

**Automatic Test Equipment (ATE):** A test equipment that send automatic test pattern generation(ATPG) to the device under test(DUT).
It has following test criterias:
  - **Parametric tests:** Measure current or voltage for the unit to ensure circuit is performing within specific parameters
  - **Functional Tests:** Evaluate functionality of the unit under operating condition
  - **Speed tests:** Assesses speed of units according to data sheet specification and sorts based on speed.

Key performance indicators of testing: Yield, Testing time and Test coverage.

##  <a name="head5_1"></a> Lab2: Building a Semiconductor Package from Scratch
**Objective:** Build a wire bond package from scratch on AEDT 3d model builder and use required materials for various components.

To start with creating 3D model click on Q3D tool from the toolbar it will create a blank 3D coordinate system.

### <a name="head5_2"></a> Die, Substrate and Die attach creation
**Die specification:**  
  - Dimension: 3mm x 3mm 
  - Position: (0,0,0)
  - Thickness: 0.2mm

To create a die select *rectangle* icon from *draw* section and create a rectangle on the XY plane.

The rectangle will show on model section on the left, right click on the rectangle and select properties to set the specification mentioned above.

It is a 2d shape so thickness can’t be applied yet.

To bring thickness select the rectangle then go to `Modeler -> Surface -> Thicken sheet`, set the thickness (0.2mm) and press ok.

Set the material of the die by double clicking on the rectangle and select dropdown next to material. Select *silicon* as material for material and press apply to set it. 

Similarly edit the name from properties and set it as die.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_e1.png)

*Fig: AEDT 3D viewer with die created*

**Substrate specification:**
  - Dimension: 5mm x 5mm
  - Position: (-1,-1,-0.1)
  - Thickness: -0.5mm

Create a rectangle on XY plane and select the dimension and position from properties section of the rectangle. Z position of -0.1mm means substrate is 0.1mm below die surface giving space for epoxy die attach.

Set the thickness by selecting `Modeler -> Surface -> Thicken sheet` and set thickness as -0.5 as surface has to go towards negative Z axis.
Set the material as *FR4_epoxy*.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_e2.png)

*Fig: AEDT 3D viewer with die and substrate created*

**Die-attach specification:**
  - Dimension: 3mm x 3mm 
  - Position: (0,0,-0.1)
  - Thickness: 0.1mm

Create the rectangle in similar way as before and set dimensions and position, for thickness set 0.1mm as it has to move on positive Z axis.
Edit the name and set material as *epoxy_kevlar_xy*.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_e3.png)

*Fig: AEDT 3D viewer with die, substrate and die-attach created*

### <a name="head5_3"></a> Die bondpad, Substrate bondpad and Wire bonding creation
In this section we create the connection between die and substrate by first adding bondpads on die and substrate as a 3D objects with the specification mentioned below.

**Die bond pad specification:**
  - Dimension: 0.2mm x 0.2mm
  - Position: (0.2,0.2,0.2) placed on top of the upper die surface close to edge
  - Thickness: 5um
  - Material: Copper

**Substrate bond pad specification:**
  - Dimension: 0.2mm x 0.2mm
  - Position: (0.2,-0.8, -0.1) placed on substrate surface aligning with die bond pad.
  - Thickness: 5um
  - Material: Copper

The bondpads are thin and added around the edges of die.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_e4.png)

*Fig: AEDT 3D viewer with showing bondpads on die and substrate*

**Wire bond creation:**
To create a wire bond select `Draw bondwire` next to rectangle section in draw section.

Then click on middle of the die bond pad to start wire bonding then click on middle of substrate bond pad to end. 

Then a pop-up shows asking for bond wire specification like bond wire type, diameter, and dimension as shown below. For now select the default settings and press ok.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_e6.png)

*Fig: AEDT 3D viewer with showing wire bonding between die and substrate bondpad*

Similarly another group of die bond pad, substrate bond pad and wire bond are created next to the current group with a gap of 0.2mm.
For wire bond assign *gold* as material.


### <a name="head5_4"></a> Wire bonding for whole design

Creating a bondpads for the whole design is a long repeating task, however there is option to duplicate existing structure along an axis saving time. Following steps are required:
  - Select a bond pad and right click then `Edit -> Duplicate -> Along line`
  - Then drag the edge along the line where you want to duplicate and left click after some space as shown above. After that mention the number of duplicates required along the line and press enter.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_e7.png)

*Fig: Duplicating a substrate bond pad along Y axis in AEDT*

  - Following this under the original element a *duplicate along section* will be formed double click that and ensure that the vector section is properly set, it specifies the space between the duplicates are done.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_e8.png)

*Fig: Five duplicate substrate bond pad along Y axis formed in a single execution*

This step is followed this for all bond pads and wire bonds along all edges.

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_e9.png)

*Fig: Bondpads and Bondwires formed on all edges using duplicate instantiation for faster creation*

### <a name="head5_5"></a> Mold addition
In final step add molding compound on the substrate. 

**Selection of Mold dimension: **
  - Position: same as that of substrate (-1,-1,-0.1)
  - Length and width: same as that of substrate 5mm x 5mm
  - Thickness: Should be above the wire bonds height 1.2mm (> Die attach thickness (0.1mm) + Die thickness(0.2mm)  + top height of wire bond(0.2mm))
    The extra margin ensures wire bonds are safe after laser marking.
  - Material used: Epoxy_kevlar_xy

![Image](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Images/Pic_e11.png)

*Fig: Final Package with Molding compound added*

[Lab file](https://github.com/Santosh3672/Packaging-Fundamentals-of-Design---Testing/blob/main/Packaging_VSD_Project_2.aedt)

## <a name="head6"></a> Acknowledgement

1. Dr. Tarun Kumar Agarwal (IITGN)

2. Kunal Ghosh (VSD)
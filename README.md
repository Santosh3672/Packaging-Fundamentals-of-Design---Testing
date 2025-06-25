# Packaging Fundamentals of Design and Testing 20-29 June 2025
VSD Workshop on Packaging fundamentals on design and testing with labs based on Ansys 20-29June 2025

## Contents
### Packaging Evolution: From Basics to 3D Integration:
#### Introduction to Packaging: Requirement and Types
#### Components of Package and its significance in semiconductor cycle
#### Overview of different types of Packaging technologies
#### Comparative analysis and selecting the righ Package type

## Packaging Evolution: From Basics to 3D Integration:
### Introduction to Packaging: Requirement and Types
Packaging is the process of transforming bare semiconductor dies—fabricated on silicon wafers—into robust, functional components that can be mounted onto printed circuit boards (PCBs). It serves as a critical bridge between the microscopic world of silicon and the macroscopic realities of real-world electronics.

Need for Semiconductor Packaging
1. **Die Protection**  
   Safeguards the fragile semiconductor die from:
   - Corrosive environments  
   - Moisture ingress  
   - Mechanical shock  
   - Handling-related damage  
   
   This ensures the long-term reliability of the device.

2. **Electrical Interconnectivity**  
   Enables electrical connection of the die to external circuitry such as:
   - Printed Circuit Boards (PCBs)  
   - Other dies in multi-die systems (advanced configurations)  
   
   Techniques used include:
   - Wire bonding  
   - Flip-chip  
   - Through-Silicon Vias (TSVs)

### Components of Package and its significance in semiconductor cycle
Image here

Wire bond BGA package example

**Molding Compound** – An epoxy-based resin that encapsulates the die and wire bonds, offering mechanical protection and shielding against moisture, dust, and contaminants. 
**Substrate** – A crucial interposer that bridges the silicon die and the PCB. It contains metal traces and vias for electrical routing, and provides mechanical stability. 
**Die Attach** – Usually a thermally conductive adhesive or solder material that secures the die onto the substrate, enabling heat dissipation and mechanical anchoring. 
**Wire Bond** – Typically made of gold, copper, or aluminum, these fine wires connect the bond pads on the die to the corresponding pads on the substrate. 
**Traces** – Embedded metal lines within the substrate that carry electrical signals between the wire bonds and the external interface of the package. 


Image here
Packaging & testing in Semiconductor flow

Once silicon wafers are manufactured, individual dies are separated, packaged, and rigorously tested. This step prepares the chips for real-world integration by enabling thermal management, mechanical protection, and secure electrical interfacing with PCBs.

**Fabless companies** 
These companies focus solely on chip architecture, RTL development, physical design, and verification. Upon finalizing the design, they deliver the GDSII file to a semiconductor foundry for fabrication. They do not own wafer fabs or engage in packaging/test. 

**Outsourced Semiconductor Assembly and Test (OSAT)**
OSATs provide third-party services to fabless and IDM companies, handling wafer probing, die packaging (e.g., wire bond, flip-chip, fan-out), final testing, and delivery. 

**Integrated Device Manufacturer(IDM)**
IDMs own and manage the complete silicon lifecycle—from design to fabrication and packaging/testing. This vertically integrated model gives them more control over costs, timelines, and supply chain resilience. 

Image here

**Key Factors in Selecting the Right Semiconductor Package**:
    1. **I/O Requirements (Pin Count)**:
The number and density of input/output connections determine whether to use high-density packages (e.g., BGA, CSP) or simpler ones (e.g., QFP, SOIC). 
    2. **Thermal Performance**:
Packages must dissipate heat effectively to maintain device reliability. Materials like ceramics or metal-core substrates are preferred for high-power applications. 
    3. **Form Factor and Footprint**:
The package size must align with the PCB layout and available space—especially critical in portable and miniaturized devices. 
    4. **Reliability and Mechanical Durability**:
Influenced by environmental conditions and material choices—packages must withstand thermal cycling, vibration, moisture, and handling stress. 
    5. **Cost and Production Volume**:
There's a trade-off between performance and cost. Simpler packages may be cost-effective for high-volume products, while advanced ones (e.g., flip-chip, fan-out) suit high-performance designs despite higher expense. 
    6. **End Application Requirements**:
Automotive, aerospace, and medical devices may demand high-reliability packages with long lifespans, while consumer electronics may favor compact, cost-optimized options. 

Visual representation of the integration of Chip, Package and board
Image here

Carrier: Substrate at packaging level
Die-to-carrier interconnect: Die attach

### Overview of different types of Packaging technologies
Image here

**1. Through-Hole Mounting (THM)**
Packages with long pins that pass through holes on the PCB—ideal for prototyping and robust mechanical anchoring.
    • **DIP (Dual In-line Package)**: Two parallel rows of pins; commonly used in ICs for prototyping. 
    • **SIP (Single In-line Package)**: Pins arranged in a single row; used in resistor networks or small logic devices. 
    • **TO (Transistor Outline)**: Metal-can style for discrete transistors and power devices with excellent heat dissipation. 
    • **PGA (Pin Grid Array)**: Grid-style pin layout offering higher I/O density than DIP/SIP—used in CPUs and high-pin-count devices. 
**2. Surface Mount Technology (SMT)**
Packages designed for direct mounting on PCB surfaces—key to miniaturization and automated assembly.
    • **QFN (Quad Flat No-lead)**: Exposed thermal pad underneath; compact with excellent thermal/electrical performance. 
    • **QFP (Quad Flat Package)**: Gull-wing leads on all four sides; used for microcontrollers and ASICs. 
    • **PBGA (Plastic Ball Grid Array)**: Solder balls arranged in a grid; provides high I/O density and better thermal management. 
    • **LGA (Land Grid Array)**: Similar to BGA, but uses flat contacts instead of balls; improves electrical performance. 
    • **CSP (Chip Scale Package)**: Extremely compact—package size nearly matches die size; ideal for mobile and wearables. 
    • **PoP (Package on Package)**: Vertical stacking of packages (e.g., logic + memory); space-saving for high-functionality systems. 
    • **MCM (Multi-Chip Module)**: Multiple dies integrated in a single package for high performance and integration. 
    • **CoWoS (Chip-on-Wafer-on-Substrate)**: An advanced 2.5D packaging method enabling high-bandwidth interconnect between dies; used in high-end SoCs and AI accelerators.

**3.Advanced package substrate**:
For multiple die in a package we can also add layers between die and substrate:
    • **2D**: Two dies are connected to substrate and are connected at ball-grid level, there is a longer connection between two dies but it is better than two separate packages.
    • **2.1D**: A Redistribution layer (RDL) is put between Dies and substrate which is faster than 2D
    • **2.3D**: An organic interposer that has multiple layers is used between die and substrate. Multiple layers of interposer is helpful when there is high IO density.
    • **2.5D**: Silicon interposer is used between die and substrate
    • **3D**: Chip is put on top of another chip.

Image here


**Option for carrier**: Leadframe(DIP, QFN) . Laminate(multiple layers) , plastic, ceramic (high temp.), organic RDL, silicon, glass

Options for interconnections: 
    • Wirebond: stiching interconnects
    • Bump/solder: Connecting the die and substrate directly through bump/solder

Image here
Image here
Summary of different packages


### Comparative analysis and selecting the righ Package type
Image here

Packages left end like DIP,  QFN are low cost and easy to assemble, but they occupy large space and as we move towards the right they become compact with more IO density and are suitable for high performance, but their cost increases.
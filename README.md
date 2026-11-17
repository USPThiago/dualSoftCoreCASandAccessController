

Dual Core CAS and Access Controller

Overview

Dual Core CAS and Access Controller is the result of mine undagrad research project: "DESIGN, 
ANALYSIS AND ASSURANCE OF SAFETY-CRITICAL MULTIPROCESSOR-BASED SYSTEMS: A CASE STUDY WITH 
SOFT-CORE PROCESSORS". The goal of research was to develop a controller system to deal with
concurrence conflicts like Write After Write (WAW), Read after Write (RAW) and Write After 
Read (WAR), in multicore archtectures. For that, the atomic instruction Compare And Swap (CAS) 
was implemented and added to the instruction set archtecture of soft-cores Intel Nios II.
The dual core architecture was created by integrating two soft-cores and a shared memory, 
which was used to study the concurrence conflict access. The Access Controller was then 
developed and synchronizes conditionals writes and native load instructions of Nios II ISA
by mutual exclusion logic.

The reaserch was developed in tree steps. First of all, the dual core architecture was 
developed, synthesized on an FPGA and tested. Then, the compare and swap instruction logic
was implemented in a external component, integrated with the soft-cores by custom instruction
master bus. Finally, Access Controller module was designed and integrated with the system.

Instructions

Because the size of project files exceeds the limit accepted in github, they were divided in
smaller ones. Furthermore, some paths was too long to be added on githut, so the files were 
ziped. If you are insterested in my research and want download project files, follow the next 
two steps:
1) Download all flies, specially those who have extension .zijk (ijk an integer);
2) Unzip the zip file named "DualCoreCASandAccessController.zip"

Files Guide

Just as research development, that was divided in steps, the project files was too and 
can be associated to them. 

1) Dual Core Architecture Development: The following folders corresponds to Dual Core 
Architecture Desing.

- Nios, nios_dual_memory, nios_dual_memory and Nios_e: First attempts to generate a single core
system. 

- genius, genius2nd and geniusHarvardArchitecture: Single Core architecture implemented
with soft-core Intel Nios II. The objective of this project was to familirizare myself
with Nios II Software Build tools and Platform Designs Environment. genius2nd folder 
contain the single core base system, used to implement more complex architectures. The folders
contains too the software description of "genius" game, used to test the system in FPGA. 

- firmware_testbench: External Read System, used to depurates memorys in FPGA. 

- dual_core, dual_core_shared_mem: First functional multicore architecture developed and 
final dual core base system, respectively.

2) Compare And Swap implementation: The following folders corresponds to CAS development.

- multicore_access_controller: contains original CAS modules and a mvp of Access Controller component.
The mvp was developed because CAS logic depends of control signals, like lock and locked. In order
to test the CAS component, an simpler version of Access Controller was implemented. 

- IPcatalogHDL: contains Platform Design file of CAS IP. 

3) Access Controller Development: The following folders corresponds to Access Controller Desing.

- multicore_access_controller_v2, multicore_access_controller_v3 and multicore_access_controller_v4: 
multicore_access_controller_v2 contains WAW mutual exclusion logic implemented in Access Controller 
component, integrated to CAS and dual core base system. multicore_access_controller_v3 contains WAW, 
RAW and WAR mutual logic implemented in Access Controller component, integrated to CAS dual core base 
system. multicore_access_controller_v4 is the final version of multicore_access_controller_v3, obtained
after it's depuration.

- access_controller_rdwr: contains implementation of RAW and WAR mutual exclusion logic (not integrated with
dual core base system)
 
- defasador: consists auxiliary debug circuit, developed to test in FPGA the ingration of Access Controller, 
Compare And Swap and Nios II modules.  












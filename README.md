# vsd_fpga
This repo contains information related to the FPGA Fabric Workshop by vsdiat

In this workshop we run two designs`(counter,riscv_core)` in following tools  
- Vivado
  - implement custom logic and functional simulation
  - integrate Vivado IP in custom logic
  - How to use ILA to view waveforms
- openfpga(VTR--which has VPR framework)
  > open source framework which can be used to generate fabric for a custom FPGA.
  
  > It is a structured framework that enables the generation of a customizable FPGA fabric
  ## design flow
  ```
   1. Read the arch from XML files
   2. Link OpenFPGA architecture to VPR data
   3. Compress routing resources to identify unique models
   4. generate Verilog code or bit stream as required
   
  ```
  -  Open flow contains VTR, which uses VPR 
    - [VPR flow](VPR.md)
    - [VTR flow](VTR.md)
- SOFA `SKYWATER OpenSource FPGAs`
  - It is a series of open-source eFPGA IP cores that use `OpenFPGA` flow and map to Skywater 130nm pdk
  - [SOFA using openFPGA](sofa.md)    

In these tools (Vivado, VTR, SOFA with open FPGA flow), we analysed  the power, timing, utilization, and post-implementation netlist verification for both designs

| Design | Vivado | VTR | SOFA (QLSOFA HD)|
| -------- | -------- | -------- | --------|
| counter | | | |

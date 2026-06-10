
## SOFA Flow: 4-bit Up Counter 
### Target: QLSOFA HD eFPGA IP
### step 1 copy design to benchmark folder

```
cp counter.v  /home/naveenbhuk/SOFA/FPGA1212_QLSOFA_HD_PNR/FPGA1212_QLSOFA_HD_task/BENCHMARK/navi/
cp counter.sdc /home/naveenbhuk/SOFA/FPGA1212_QLSOFA_HD_PNR/FPGA1212_QLSOFA_HD_task/BENCHMARK/navi/
```
### step 2 - Edit `task_simulation.config`


```
 vim /home/naveenbhuk/SOFA/FPGA1212_QLSOFA_HD_PNR/FPGA1212_QLSOFA_HD_task/config/task_simulation.conf
```
few imp set parameter  :
1. ARCHITECTURE  ---xml file
2. BENCHMARK     --- *.v file
3. SYNTHESIS_PARAM --- top module
4. task_config
   
changed the counter path and top to up counter
```vim FPGA1212_QLSOFA_HD_task/generate_testbench.openfpga```
make runOpenFPGA  from FPGA1212_qlsofa_hd_pnr



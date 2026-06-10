
## SOFA Flow: 4-bit Up Counter 
### Target: QLSOFA HD eFPGA IP
### step 1 copy design to benchmark folder

```
cp counter.v  /home/naveenbhuk/SOFA/FPGA1212_QLSOFA_HD_PNR/FPGA1212_QLSOFA_HD_task/BENCHMARK/navi/
cp counter.sdc /home/naveenbhuk/SOFA/FPGA1212_QLSOFA_HD_PNR/FPGA1212_QLSOFA_HD_task/BENCHMARK/navi/
```
```
cd /home/naveenbhuk/SOFA/FPGA1212_QLSOFA_HD_PNR```
```vim FPGA1212_QLSOFA_HD_task/config/task_simulation.conf ```
changed the counter path and top to up counter
```vim FPGA1212_QLSOFA_HD_task/generate_testbench.openfpga```
make runOpenFPGA  from FPGA1212_qlsofa_hd_pnr




## SOFA Flow:using  4-bit Up Counter 
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
### step 3 Edit 'generate_testbench.openfpga'
```vim FPGA1212_QLSOFA_HD_task/generate_testbench.openfpga```
Add an option to the vpr command
```
vpr ${VPR_ARCH_FILE} ${VPR_TESTBENCH_BLIF} \
    --clock_modeling ideal \
    --device ${OPENFPGA_VPR_DEVICE_LAYOUT} \
    --route_chan_width ${OPENFPGA_VPR_ROUTE_CHAN_WIDTH} \
    --absorb_buffer_luts off \
    --sdc_file /home/naveenbhuk/SOFA/BENCHMARK/navi/counter.sdc
```
### step 4 -RUN
```
cd /home/naveenbhuk/SOFA/FPGA1212_QLSOFA_HD_PNR
make runOpenFPGA
```



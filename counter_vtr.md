till post simuation
```
$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py counter.v  $VTR_ROOT/vtr_flow/arch/timing/EArch.xml --route_chan_width 100 -sdc_file /home/navi/FPGA/vtr_designs/counter/counter.sdc --gen_post_synthesis_netlist on
```
- to see arch log
grep -i "arch\|EArch" temp/vpr.out
power
```

$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py \
    counter.v \
    $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
    -power -cmos_tech  /home/kunalg123/Desktop/openFPGA/openfpga_flow/tech/PTM_45nm/45nm.xml  \
    ./results/vpr \
    --route_chan_width 100

```
results
>Utilization

```
grep -A 15 "Circuit Statistics" temp/vpr.out
```
```
 $VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py counter.v  $VTR_ROOT/vtr_flow/arch/timing/EArch.xml --route_chan_width 100 -sdc_file /home/navi/FPGA/vtr_designs/counter/counter.sdc -power -cmos_tech $VTR_ROOT/vtr_flow/tech/PTM_45nm/45nm.xml
```

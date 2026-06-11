till post simuation
```
$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py \
  counter.v \
  $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
  -temp_dir ./results \
  --route_chan_width 100 \
  --sdc_file counter.sdc \
  
  --gen_post_synthesis_netlist on

```

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


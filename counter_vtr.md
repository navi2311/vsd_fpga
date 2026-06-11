```
$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py \
  counter.v \
  $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
  -temp_dir ./results \
  --route_chan_width 100 \
  --sdc_file counter.sdc \
  
  --gen_post_synthesis_netlist on

```

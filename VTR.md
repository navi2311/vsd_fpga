```$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py  counter.v $VTR_ROOT/vtr_flow/arch/timing/EArch.xml -temp_dir ./results --route_chan_width 100 --sdc_file counter.sdc  -ending_stage odin```
inputs ---- .xml,.v
flags_used ---- 
-temp_dir to set output log files
----route_chan_width 100 routhing width flag
--sdc_file counter.sdc --- sdc file passing
-ending_stage odin --- end at odin stage

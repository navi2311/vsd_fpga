```$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py  counter.v $VTR_ROOT/vtr_flow/arch/timing/EArch.xml -temp_dir ./results --route_chan_width 100 --sdc_file counter.sdc  -ending_stage odin```
inputs ---- .xml,.v
flags_used ---- 
-temp_dir to set output log files
----route_chan_width 100 routhing width flag
--sdc_file counter.sdc --- sdc file passing
-ending_stage odin --- end at odin stage


##################################
output 
<img width="2497" height="605" alt="image" src="https://github.com/user-attachments/assets/89edf571-14c8-4cbb-88cd-6697c817aa30" />

####ABC
```$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py ./results/counter.odin.blif $VTR_ROOT/vtr_flow/arch/timing/EArch.xml -temp_dir ./results/abc --route_chan_width 100 --sdc_file -starting_stage abc -ending_stage abc```

****<img width="2535" height="805" alt="image" src="https://github.com/user-attachments/assets/bd1d4786-0b45-4153-9c5e-996dec4c0806" />

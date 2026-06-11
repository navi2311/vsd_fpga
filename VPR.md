# Day 2
## VPR
> VTR `Veristale Place and Route` is an open source tool designed for exploration of new FPGA architectures and CAD algorithmis at ` packing,placement and routing ` phases
### inputs
- FPGA architecture file (.xml)
- technology mapped user defined circuit
## 
then it performs 
- packing
- placement
- routing
- analysis
to map circuit onto the fpga
### commands to runs
> `vpr arch_file .blif_file` command to run vpr ---min two inputs required

- to run without gui
```
$VTR_ROOT/vpr/vpr \
    $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
    $VTR_ROOT/vtr_flow/benchmarks/blif/tseng.blif \
    --route_chan_width 100
```
- with gui
$VTR_ROOT/vpr/vpr \
    $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
    $VTR_ROOT/vtr_flow/benchmarks/blif/tseng.blif \
    --route_chan_width 100 \
    --analysis --disp on

  ``
- timing analysis
  `'
- post_implenmation
  ``


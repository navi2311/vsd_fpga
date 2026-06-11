# Day 2
## VPR
> VTR `Veristale Place and Route` is an open source tool designed for exploration of new FPGA architectures and CAD algorithmis at ` packing,placement and routing ` phases
### inputs
- FPGA architecture file (.xml)
- technology-mapped user-defined circuit
## VPR STAGES
| stage | input | output | command |
|------|---------|----------|----|
| `pack` | *.v | *.net | --pack |
| `place` | *.net | *.place | --place |
| `route` | *.place | *.route | -- route |

> note: with VPR pass input and command option if we want to run incremental

### commands to run 
> `vpr arch_file .blif_file` command to run vpr ---min two inputs required

- to run without a GUI
```
$VTR_ROOT/vpr/vpr \
    $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
    $VTR_ROOT/vtr_flow/benchmarks/blif/tseng.blif \
    --route_chan_width 100
```
- with gui
```
$VTR_ROOT/vpr/vpr \
    $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
    $VTR_ROOT/vtr_flow/benchmarks/blif/tseng.blif \
    --route_chan_width 100 \
    --analysis --disp on
```
  
- timing analysis
```
--sdc_file "path to file"
```
- post_implenmation
  ```
  --gen_post_synthesis_netlist on
  ```


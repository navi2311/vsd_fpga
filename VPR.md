# Day 2
## VPR
> VTR `Veristale Place and Route` is an open source tool designed for exploration of new FPGA architectures and CAD algorithmis at ` packing,placement and routing ` phases
### inputs
- FPGA architecture file (.xml)
- technology-mapped user-defined circuit
## VPR STAGES
| stage | input & output| 
|------|---------|
| `pack` | RTL source |
| `place` | Target FPGA architecture |
| `route` | Output directory for logs and intermediate files |
| `analysis` | Fixed routing channel width |

to map the circuit onto the FPGA
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


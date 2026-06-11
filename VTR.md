
## VTR Flow: 
>command to run all stages
```
$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py counter.v   $VTR_ROOT/vtr_flow/arch/timing/EArch.xml   --route_chan_width 100   --sdc_file /home/navi/FPGA/vtr_designs/counter/counter.sdc   -temp_dir /home/navi/FPGA/vtr_designs/counter/results   --gen_post_synthesis_netlist on

```
VTR flow usage incremental using a counter example
### Stage 1 — ODIN II/yosys/parmys (RTL → BLIF)

```bash
 $VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py counter.v   $VTR_ROOT/vtr_flow/arch/timing/EArch.xml   --route_chan_width 100   --sdc_file /home/navi/FPGA/vtr_designs/counter/counter.sdc   -temp_dir /home/navi/FPGA/vtr_designs/counter/results/stage1   -start parmys   -end parmys

```

| Flag | Purpose |
|------|---------|
| `counter.v` | RTL source |
| `EArch.xml` | Target FPGA architecture |
| `-temp_dir ./results` | Output directory for logs and intermediate files |
| `--route_chan_width 100` | Fixed routing channel width |
| `--sdc_file counter.sdc` | Timing constraints |
| `-ending_stage parmys ` | Stop after parmys synthesis (produces `.parmys.blif`) |

**Output:**
<img width="550" height="49" alt="image" src="https://github.com/user-attachments/assets/12af6380-7a89-408b-8f4a-2e2ea38d4e4a" />

---

### Stage 2 — ABC (Logic Optimization → Mapped BLIF)

```bash
$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py results/stage1/counter.parmys.blif   $VTR_ROOT/vtr_flow/arch/timing/EArch.xml   --route_chan_width 100   --sdc_file /home/navi/FPGA/vtr_designs/counter/counter.sdc   -temp_dir /home/navi/FPGA/vtr_designs/counter/results/stage2   -start abc   -end abc
```




**Output:**
****<img width="480" height="74" alt="image" src="https://github.com/user-attachments/assets/d41128b4-e89d-4530-9b9c-794b56481514" />



### Stage 3 — VPR (Pack → Place → Route → STA)

```bash
$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py \
  ./results/abc/counter.odin.abc.blif \
  $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
  -temp_dir ./results/vpr \
  --route_chan_width 100 \
  --sdc_file counter.sdc \
  -starting_stage vpr \
  -ending_stage vpr \
  --timing_report_detail detailed \
  --timing_report_npaths 10
```

| Flag | Purpose |
|------|---------|
| `--timing_report_detail detailed` |  |
| `--timing_report_npaths 10` | Report top 10 critical paths |


# Critical path and Fmax
cat results/vpr/report_timing.setup.rpt

# Utilization
cat results/vpr/packing_pin_util.rpt


# post netlist
```
$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py \
  counter.v \
  $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
  -temp_dir ./results \
  --route_chan_width 100 \
  --sdc_file counter.sdc \
  
  --gen_post_synthesis_netlist on
  ```

# power
We have to ace the engine
```
$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py \
    counter.v \
    $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
    -power -cmos_tech  /home/kunalg123/Desktop/openFPGA/openfpga_flow/tech/PTM_45nm/45nm.xml  \
    ./results/vpr \
    --route_chan_width 100
```




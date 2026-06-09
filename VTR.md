## VTR Flow: 4-bit Counter

### Stage 1 — ODIN II (RTL → BLIF)

```bash
$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py \
  counter.v \
  $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
  -temp_dir ./results \
  --route_chan_width 100 \
  --sdc_file counter.sdc \
  -ending_stage odin
```

| Flag | Purpose |
|------|---------|
| `counter.v` | RTL source |
| `EArch.xml` | Target FPGA architecture |
| `-temp_dir ./results` | Output directory for logs and intermediate files |
| `--route_chan_width 100` | Fixed routing channel width |
| `--sdc_file counter.sdc` | Timing constraints |
| `-ending_stage odin` | Stop after ODIN II synthesis (produces `.odin.blif`) |

**Output:**
<img width="2497" height="605" alt="image" src="https://github.com/user-attachments/assets/89edf571-14c8-4cbb-88cd-6697c817aa30" />

---

### Stage 2 — ABC (Logic Optimization → Mapped BLIF)

```bash
$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py \
  ./results/counter.odin.blif \
  $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
  -temp_dir ./results/abc \
  --route_chan_width 100 \
  -starting_stage abc \
  -ending_stage abc
```




**Output:**
****<img width="2535" height="805" alt="image" src="https://github.com/user-attachments/assets/bd1d4786-0b45-4153-9c5e-996dec4c0806" />


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




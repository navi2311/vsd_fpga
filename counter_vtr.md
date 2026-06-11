# post simulation
<img width="599" height="456" alt="image" src="https://github.com/user-attachments/assets/e740bed2-0fc6-472d-b2f8-52b5d2521b6b" />




# power
```

$VTR_ROOT/vtr_flow/scripts/run_vtr_flow.py \
    counter.v \
    $VTR_ROOT/vtr_flow/arch/timing/EArch.xml \
    -power -cmos_tech  /home/kunalg123/Desktop/openFPGA/openfpga_flow/tech/PTM_45nm/45nm.xml  \
    ./results/vpr \
    --route_chan_width 100

```
<img width="353" height="258" alt="image" src="https://github.com/user-attachments/assets/400af4cf-8bb5-459e-a658-e27c1830c73d" />


# Utilization

```
grep -A 15 "Circuit Statistics" temp/vpr.out
```
<img width="619" height="188" alt="image" src="https://github.com/user-attachments/assets/abd527e2-b42d-4d1e-8116-8c0911fa0a4b" />

<img width="668" height="296" alt="image" src="https://github.com/user-attachments/assets/24779c8c-ec5e-4756-960f-62a6c2f5e365" />




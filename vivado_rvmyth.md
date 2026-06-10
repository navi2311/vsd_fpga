```
vivado &
create_project project_1 /home/naveenbhuk/workshop/fpga_workshop_collaterals/Day3/project_1 -part xc7a35tcpg236-1
```
```
set_property board_part digilentinc.com:basys3:part0:1.1 [current_project]
add_files -norecurse /home/naveenbhuk/workshop/fpga_workshop_collaterals/Day3/mythcore_test_no_ILA.v
add_files -fileset constrs_1 -norecurse /home/naveenbhuk/workshop/fpga_workshop_collaterals/Day3/constraints.xdc
update_compile_order -fileset sources_1
```

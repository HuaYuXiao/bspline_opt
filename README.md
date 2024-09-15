# bspline_opt

![HitCount](https://img.shields.io/endpoint?url=https%3A%2F%2Fhits.dwyl.com%2FHuaYuXiao%2Fbspline_opt.json%3Fcolor%3Dpink)
![Static Badge](https://img.shields.io/badge/ROS-noetic-22314E?logo=ros)
![Static Badge](https://img.shields.io/badge/C%2B%2B-14-00599C?logo=cplusplus)
![Static Badge](https://img.shields.io/badge/Ubuntu-20.04.6-E95420?logo=ubuntu)

The bspline_opt package, submodule of `Fast-Planner` & `EGO-Planner` & `PE-Planner`

## Introduction

### Fast-Planner

- [non_uniform_bspline.cpp](src%2Fnon_uniform_bspline.cpp)
- [bspline_optimizer_fast.cpp](src%2Fbspline_optimizer_fast.cpp)

### EGO-Planner

- [uniform_bspline.cpp](src%2Funiform_bspline.cpp)
- [bspline_optimizer_ego.cpp](src%2Fbspline_optimizer_ego.cpp)

### PE-Planner

- [bspline_optimizer_pe.cpp](src%2Fbspline_optimizer_pe.cpp)


## Installation

```bash
git clone https://gitee.com/hyx020222/bspline_opt.git  ~/easondrone_ws/plan/bspline_opt
cd ~/easondrone_ws && catkin_make --source plan/bspline_opt --build plan/bspline_opt/build
```

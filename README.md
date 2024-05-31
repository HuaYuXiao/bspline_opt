# bspline_opt

The bspline_opt package, submodule of `Fast-Planner` & `EGO-Planner` & `PE-Planner`

![HitCount](https://img.shields.io/endpoint?url=https%3A%2F%2Fhits.dwyl.com%2FHuaYuXiao%2Fbspline_opt.json%3Fcolor%3Dpink)
![Static Badge](https://img.shields.io/badge/ROS-noetic-22314E?logo=ros)
![Static Badge](https://img.shields.io/badge/C%2B%2B-14-00599C?logo=cplusplus)
![Static Badge](https://img.shields.io/badge/Ubuntu-20.04.6-E95420?logo=ubuntu)


## Introduction

### Fast-Planner

- [non_uniform_bspline.cpp](src%2Fnon_uniform_bspline.cpp)
- [bspline_optimizer_fast.cpp](src%2Fbspline_optimizer_fast.cpp)

### EGO-Planner

- [uniform_bspline.cpp](src%2Funiform_bspline.cpp)
- [bspline_optimizer_ego.cpp](src%2Fbspline_optimizer_ego.cpp)

### PE-Planner

- [bspline_optimizer_pe.cpp](src%2Fbspline_optimizer_pe.cpp)


## Release Note

- v1.3.0: support `PE-Planner`
- v1.2.0: support `Fast-Planner`
- v1.1.1(beta): support `max_jerk`
- v1.1.0: support `EGO-Planner`


## Installation

prerequisite:

- `path_searching`
- `plan_env`

```bash
catkin_make install --source Planning/bspline_opt --build Planning/bspline_opt/build
```

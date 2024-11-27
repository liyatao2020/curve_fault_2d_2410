# Project Overview

This project investigates the impact of mining on the dynamic rupture of non-planar faults (induced seismic events) and the spatiotemporal evolution of the resulting seismic waves. It also assesses the influence of these seismic waves on mining workfaces. Utilizing the PyLith software, a refined mesh model has been developed, and a series of simulations have been conducted to explore mining-induced dynamic fault ruptures in heterogeneous layered media. This README provides detailed insights into the model configuration and processing methods employed in the study.

## Project File Organization

- `mesh.exo`: Contains the completed fine mesh model file.
- `step00.cfg`: PyLith configuration file for precise control of simulation startup and execution.
- `fault_slabtop_slipweakening.spatialdb`: Defines key parameters used in the simulation, such as friction coefficient and cohesion.

## Analysis Parameters

The current analysis is based on the mechanical parameters outlined in the following tables. Using PyLith 2.2.2, we simulate the spatiotemporal evolution of dynamic slip along faults influenced by mining operations and evaluate the impact of seismic waves on mining workfaces.

### Table 1: Summary of Elastic Parameters in the Simulation

| Layers        | Density (kg/m³) | Shear Modulus G (GPa) | Poisson's Ratio (ν) | Young's Modulus (GPa) | Vs (km/s) | Vp (km/s) |
|---------------|----------------|----------------------|---------------------|---------------------|-----------|-----------|
| Overlying strata | 2700           | 7.2                  | 0.23                | 17.6                | 1.628     | 2.749     |
| Hard strata   | 2707           | 10.5                 | 0.22                | 25.6                | 1.970     | 3.288     |
| Main roof     | 2807           | 11.5                 | 0.21                | 27.9                | 2.028     | 3.347     |
| Immediate roof| 2173           | 2.1                  | 0.24                | 5.1                 | 0.977     | 1.670     |
| Coal seam     | 1440           | 1.4                  | 0.16                | 3.3                 | 0.994     | 1.562     |
| Direct bottom | 2673           | 9.1                  | 0.25                | 22.7                | 1.841     | 3.189     |
| Basic bottom  | 2461           | 9.1                  | 0.35                | 24.6                | 1.925     | 4.007     |

### Table 2: Slip Weakening Law Used in the Simulation (One Case)

| Static Friction Coefficient | Dynamic Friction Coefficient | Slip Weakening Distance Dc (m) | Cohesion C (MPa) |
|-----------------------------|------------------------------|------------------------------|------------------|
| 0.45                        | 0.36397                      | 0.001                        | 0                |

## Running Guide

1. Refer to the official PyLith documentation to ensure the correct installation of PyLith version 2.2.2.
2. In the project root directory, start the simulation process with the following command: `pylith step00.cfg`
3. After the simulation is complete, all results will be output to the `output` folder.

## Result Output and Viewing

After the simulation ends, you can find the following `.xmf` formatted result files in the `output` folder:

- `model-all-disp.xmf`
- `fault_traction.xmf`
- `material-f1.xmf`
- `material-h1.xmf`
- `...`

1. For convenient viewing and sharing, the simulation results have also been uploaded to: [https://github.com/liyatao2020/curve_fault_2d_2410](https://github.com/liyatao2020/curve_fault_2d_2410)
2. These files record various data during the simulation process in detail, and you can use software like ParaView for viewing and analysis.

### Result Viewing Method:

1. Open the ParaView software.
2. Import `.xmf` files to view the simulation results.
3. Utilize ParaView's rich toolset, such as slicing, isosurfacing, etc., to showcase the simulation data in all directions.
4. If further data processing is required, you can use ParaView's Filter function to export the data in CSV format, providing convenience for subsequent in-depth analysis, such as calculating slip distribution.

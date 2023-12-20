Steps to reproduce NREL5MW - FSI - demo

1. Run OpenFAST using the C++ API inside the `openfast_run` folder like so `openfastcpp inp.yaml`. This runs OpenFAST with AeroDyn for 1 revolution at 15m/s. OpenFAST is set to blend from BEM (AeroDyn) to CFD loads at 3 revolutions over 1/4th of a revolution.

2. Copy the `.chkp`, `.dll.chp`, and `.nc` files to the `fsi_pitch` folder and run the `exawind` solver like so

``` shell
srun -n 1152 exawind --nwind 360 --awind 792 nrel5mw-01.yaml &> log
```

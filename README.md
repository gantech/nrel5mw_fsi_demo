Steps to reproduce NREL5MW - FSI - demo

1. Run OpenFAST using the C++ API inside the `openfast_run` folder like so `openfastcpp inp.yaml`. This runs OpenFAST with AeroDyn for 1 revolution at 15m/s. OpenFAST is set to blend from BEM (AeroDyn) to CFD loads at 3 revolutions over 1/4th of a revolution.

2. Copy the `.chkp`, `.dll.chp`, and `.nc` files to the `fsi_pitch` folder and run the `exawind` solver like so

``` shell
srun -n 1152 exawind --nwind 360 --awind 792 nrel5mw-01.yaml &> log
```

Versions
--------

You'd need the latest nalu-wind, amr-wind, exawind-driver repositories as of this commit for this demo. OpenFAST needs this branch (https://github.com/gantech/OpenFAST/tree/f/br_fsi_2) The OpenFAST model of the NREL 5MW in this repository is really old (OpenFAST-3.0). If you manage to update the model of OpenFAST to work with the `dev` branch, please use the `dev` branch of OpenFAST as well (https://github.com/OpenFAST/openfast/tree/dev).






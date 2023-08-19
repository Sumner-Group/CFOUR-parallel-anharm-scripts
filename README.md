# CFOUR-parallel-anharm-scripts
Scripts for running parallel anharmonic calculations using the Slurm/Torque workload managers. They have
been tested using version 2.0-beta.
These scripts are clearly indebted to the scripts provided by the CFour developers.
http://slater.chemie.uni-mainz.de/cfour/index.php?n=Main.ScriptsForDoingVPT2CalculationsByFiniteDifferencesInParallel

I provided a ZMAT file similar to the one found at the above link. The main differenece that it performs analytic frequencies, 
not finite difference. The scripts should be run in order:

1) run-cfour-1.script: submits a job to queue that will perform an analytic frequency calculation and will provide ZMAT
files containing displaced geometries for higher order derivative calculations. If run correctly you should have 3N-6 new ZMAT
files (N is the number of atoms).

2) run-cfour-2.script: submits 3N-6 independent jobs to queue, creates one directory submits one job for each displaced geometry
created by the first script

3) run-cfour-3.script: collects all the data and performs final calculations. This is not submitted to queue and puts data into a 
directory called "final"

**Do you want to cite this work?**
---
Bunn, H.; Soliday, R. M.; Sumner, I.; Raston, P. L. “Far-infrared spectroscopic characterization of anti-vinyl alcohol” The Astrophysical Journal, 2017, 847, 67-72. [doi:10.3847/1538-4357/aa8870](https://doi.org/10.3847/1538-4357/aa8870)

[![DOI](https://zenodo.org/badge/100744168.svg)](https://zenodo.org/badge/10.5281/zenodo.845888/100744168)


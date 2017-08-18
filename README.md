# CFOUR-parallel-anharm-scripts
Scripts for running parallel anharmonic calculations using the Slurm/Torque workload managers
These scripts are obviously based on the scripts provided by the CFour developers
http://slater.chemie.uni-mainz.de/cfour/index.php?n=Main.ScriptsForDoingVPT2CalculationsByFiniteDifferencesInParallel
I provided a ZMAT file similar to the one found at the above link. The main differenece that it performs analytic frequencies, 
not finite difference. The scripts should be run in order:

1) run-cfour-1.script: submits a job to queue that will perform an analytic frequency calculation and will provide ZMAT
files containing displaced geometries for higher order derivative calculations

2) run-cfour-2.script: submits forked jobs to queue, one job for each displaced geometry created by the first script

3) run-cfour-3.script: collects all the data and performs final calculations. This is not submitted to queue

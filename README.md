# the-parallelization-of-TRIGRS
We use OpenMP and MPI to further parallelize the latest version of TRIGRS model, TRIGRS 2.1, shortening its running time.

The parallelization implementation:
1) We employ OpenMP to optimize the computation part in TRIGRS 2.1. In addition to partitioning the grid cells with MPI, we further partition the grid cells with OpenMP to achieve a thread-level parallelization.
2)We use MPI to parallelize two parts in TRIGRS 2.1: the file writing in the main program and the subroutine rnoff_p, which calculates runoff routing, actual infiltration rates, and output actual infiltration. They both include a do-loop calculation. The former's elapsed time is determined by $nout$; the latter's is determined by $nper$. $nout$ is the number of rainfall moments that are ultimately output; $nper$ is the number of rainfall periods. Both parameters are set in the configuration file.
The codes, both the original code and the optimized code, can be run directly, which includes the data we experimented.

Compiling and running steps: 
1) load the compiling environment (module load MPI module load GSL)
2) make (generate tpx, prg) 
3) yhrun. /tpx
4) for original code: yhrun -n ./prg
   for optimized code:yhbatch - N - n - c. / run1.sh 

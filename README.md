# the-parallelization-of-TRIGRS
We use OpenMP and MPI to further parallelize the latest version of TRIGRS model, TRIGRS 2.1, shortening its running time.

Directories:

optimized code : storing the codes after optimized and the data.
original code: storing the codes before optimized and the data.

Compiling and running steps: 
1) load the compiling environment (load MPI, GSL)
2) make (generate tpx, prg) 
3) yhrun. /tpx
4) for original code: yhrun -n ./prg
   for optimized code:yhbatch - N - n - c. / run1.sh 

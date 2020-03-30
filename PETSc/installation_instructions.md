## PETSc installation instructions
### Compiling
The steps to properly compile PETSc on JURECA are this ones:

1. Purge the previous loaded packaged  
`module --force purge`
1. Load the needed packaged \
`module load Architecture/KNL` \
`module load intel-para` \
`module load CMake` \
The KNL (Intel Knights Landing) architecture allows to cross-compile PETSc

2. Run the configure script ([runPETScConfig](runPETScConfig.txt)) \
`./runPETScConfig`  
  **Disclaimer**:   This configure script has been created by looking for the options and flags the developers have
   used to compile
   a previous PETSc version on JURECA. If new flags are needed, one should load the default PETSc version  
    `module load PETSc`  
     and then go use the options defined at the compilation log file at   
     `$PETSC_DIR/lib/petsc/conf/reconfigure-arch-linux2-c-opt.py`.
3. Run the PETSc make \
`make all` \
`make test`

### Usage with PFLOTRAN

Once PETSc is compiled, one can install PFLOTRAN setting up the newly compiled PETSc environmental variables:

`export PETSC_DIR=/PETSc_install_dir`  
`export PETSC_ARCH=name_given_to_the_compilation`

Then, one can install PFLOTRAN as usual (`make pflotran`).

To run a model using PFLOTRAN on JURECA one can send a batch job using the [run_JURECA.batch](run_JURECA.batch) template
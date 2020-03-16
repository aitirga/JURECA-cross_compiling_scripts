## PETSc installation instructions

The steps to properly compile PETSc on JURECA are this ones:

1. Load the needed packaged \
`module load Architecture/KNL` \
`module load intel-para` \
`module load CMake` \
The KNL (Intel Knights Landing) architecture allows to cross-compile PETSc

2. Run the configure script ([runPETScConfig](runPETScConfig.txt)) \
`./runPETScConfig` \
The key is to include *--with-blas-lapack-dir=$MKLROOT/lib/intel64 \*

3. Run the PETSc make \
`make all` \
`make test`
# OpenFAST

## CMake Build Instructions

```
git clone https://github.com/OpenFAST/OpenFAST.git
cd OpenFAST
mkdir build && cd build
cmake ../ 
make 
```

To build on Peregrine, use the following sript:
```
module purge
module use /nopt/nrel/apps/modules/candidate/modulefiles/
module load impi-intel/2017.0.2 mkl/2017.0.2 cmake/3.3.2
module unload epel
module list

cmake ../ -DCMAKE_INSTALL_PREFIX=[Your working Directory] -DBLAS_blas_LIBRARY=/nopt/intel/psxe2017u2/compilers_and_li
braries_2017.2.174/linux/mkl/lib/intel64 -DCMAKE_Fortran_FLAGS_RELEASE="-threads -O2 -g [-qopenmp] " 
```

### Current CMake Options 

* `DOUBLE_PRECISION` - Enable/disable `-DDOUBLE_PRECISION` flag (Default: ON)
* `USE_DLL_INTERFACE` - Enable dynamic library loading capability (Default: ON)
* `CMAKE_BUILD_TYPE` - Release, Debug builds (Default: Release)
* `CMAKE_INSTALL_PREFIX` - Set desired installation directory
* `BUILD_SHARED_LIBS` - Enable/disable building shared libraries (Default: OFF)

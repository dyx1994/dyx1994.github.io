# CMake Note

---------
**CMake** is not a build system, but a build system generator. It is a cross-platform build tool.

## Build process from the user's perspective

The build process usually run in the linux command as follows:

```bash
1. cd <project_folder>
2. mkdir build
3. cd build
4. cmake ..
5. make
```

The build process is  defined  in `CMakeLists.txt` and childrens' `src/CMakeLists.txt` 

If you want a clean build, and rebuild the program:

``` bash
1. cd projects/build
2. make clean [remove generated binaries]
3. rm -rf * [make sure you are in build folder]
```

Short way (if you are in  `project /`)

```bash
rm -rf build/
```

## Steps for writing a CMakeLists.txt file

### Adding a version number

We need to add cmake version in the beginning and set the project name.

```bash
# set the cmake version, check the cmake version before writing CMakeLists.txt
cmake_minimum_required(VERSION 3.10)
# set the project name and version
project( Demo VERSION 1.0)
```

### Specify the CPP standard

We need to explicitly state C++ standard in the file. Make sure to add the `CMAKE_CXX_STANDARD` declartions above the call to `add_executable`

```bash
# specify the c++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)
```

### Specify the installation location of the object file:

1. Linux command (recommended)
  
```bash
cmake -DCMAKE_INSTALL_PREFIX=[Install path]
```

2. Set variables in `CMakeLists.txt`

```bash
set(CMAKE_INSTALL_PREFIX [install path])
```
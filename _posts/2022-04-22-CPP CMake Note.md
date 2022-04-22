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

### Adding a library

Basiclly, functions are contained in **src**, it's better to create a CMakeLists.txt in **src** file. In the **src/CMakeLists.txt**, we can create a library.

```bash
add_library(functions sum.cpp subtract.cpp)
```

In the root path's CMakeLists.txt

```bash
        # tell cmake where to find header file *.hpp *.h
        include_directories(include/)
        # add the library path 
        add_subdirectory(src)
        # add the executable 
        add_executable(main main.cpp)
        # link lib and main
        target_link_libraries(main functions)

```

### Specify the installation location of the object file:

 - Linux command (recommended)
  
```bash
cmake -DCMAKE_INSTALL_PREFIX=[Install path]
```

- Set variables in `CMakeLists.txt`

```bash
set(CMAKE_INSTALL_PREFIX [install path])
```

### Installation 

`CMakeLists.txt` 

```bash
        # install executable file to install file
        install(TARGETS main DESTINATION bin)
        install(DIRECTORY ${CMAKE_SOURCE_DIR}/include DESTINATION include)
```

`src/CMakeLists.txt`

```bash
        install(TARGETS ipb_arithmetic DESTINATION lib) 
```

Rebuild the program and make installation:

```bash
        cd build/
        cmake ..
        make
        make install ..
```
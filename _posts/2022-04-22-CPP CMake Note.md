# CMake Note

---------
**CMake** is not a build system, but a build system generator. It is a cross-platform build tool.

## Build a CMake project

**Build process** from the user's perspective

```shell
1. cd <project_folder>
2. mkdir build
3. cd build
4. cmake ..
5. make
```

The build process is  defined  in `CMakeLists.txt` and childrens' `src/CMakeLists.txt` 

If you want a clean build, and rebuild the program:

``` shell
1. cd projects/build
2. make clean [remove generated binaries]
3. rm -rf * [make sure you are in build folder]
```

Short way (if you are in  `project /`)

```shell
rm -rf build/
```


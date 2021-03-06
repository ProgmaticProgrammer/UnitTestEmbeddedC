# UnitTest EmbeddedC
This is an example of doing a UnitTest project using [googltest](https://github.com/google/googletest/).

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](/LICENSE)

[<img src="https://travis-ci.com/images/logos/TravisCI-Full-Color.png" height="25"/>
<img src="https://dka575ofm4ao0.cloudfront.net/pages-transactional_logos/retina/16896/ApwXsQaJT16xVdsGs7aY" height="25"/>](#references)

| Build status          | Systems / Compilers         |
| ------------- | ------------------------------------------ |
| [![Build Status](https://travis-ci.com/ProgmaticProgrammer/UnitTestEmbeddedC.svg?branch=master)](https://travis-ci.com/ProgmaticProgrammer/UnitTestEmbeddedC) | Linux (gcc7) |
| [![Visual Studio Builds](https://ci.appveyor.com/api/projects/status/t6i95u07gw1gqhql/branch/master?svg=true)](https://ci.appveyor.com/project/ProgmaticProgrammer/unittestembeddedc/branch/master)       | Windows (Visual Studio 2017) |


![Alt text](/doc/screenshot.jpg?raw=true "Optional Title")

## Info

[CMake](https://cmake.org/) is the chosen build system using [ctest](https://cmake.org/Wiki/CMake/Testing_With_CTest).

[VSCode](https://code.visualstudio.com/) is the chosen development IDE.

## Library used
- [googltest](https://github.com/google/googletest/) for unit test system. (as submodule)

## Project Structure
```
UnitTestEmbeddedC/
├── CMakeLists.txt
├── README.md
├── doc
├── .vscode
├── googletest
│   ├── CMakeLists.txt
│   └── ...
├── src
│   ├── Array.c
│   ├── Array.h
│   └── ...
│── test
│   ├── UnitTestFiles
│   │   └── ...
│   ├── MockFiles
│   │   └── ...
│   ├── Main.cpp
│   └── ...
```
Directory structure:
- `src`    : Directory for source code under test.
- `test`   : Directory for test code, including unit test and mock files.
- `doc`    : Directory for documents.
- `.vscode`: Directory for VSCode configuration.
- `googletest`: Directory for submodule googletest.
- `CMakeLists.txt`: CMake file.
- `README.md`: This file.

## How to start
#### Clone the repository recursively
```shell
  mkdir my_project
  cd my_project
  git clone https://github.com/ProgmaticProgrammer/UnitTestEmbeddedC.git --recursive --progress -v
```
#### Open the repository in VSCode
 - Open a Developer Command Prompt (VS 2017)

 ![Alt text](/doc/cmdpromt.jpg?raw=true "Optional Title")
 
 
 - Open the VSCode from the Command Prompt
```shell
  cd my_project\UnitTestEmbeddedC
  code .
```
 ![Alt text](/doc/code.jpg?raw=true "Optional Title")

 
#### Build/Run/Test in VSCode
 ![Alt text](/doc/RunTask.jpg?raw=true "Optional Title")
 ![Alt text](/doc/tasks.jpg?raw=true "Optional Title")
 - Choose the `cmake configure` to confgure cmake
 - Choose the `cmake build` to build vs2017 target
 - Choose the `ctest run` to configure/build/test as one go

   ![Alt text](/doc/all-in-one.jpg?raw=true "Optional Title")
   
## Develop
#### Click Explorer or (Ctrl+Shift+E) to browser source code

   ![Alt text](/doc/explorer.jpg?raw=true "Optional Title")

#### Click Source Control or (Ctrl+Shift+G) to browser source control

   ![Alt text](/doc/sourcecontrol.jpg?raw=true "Optional Title")
   
#### Click Run or (Ctrl+Shift+D) to debug source code

   ![Alt text](/doc/debug.jpg?raw=true "Optional Title")
   
#### If GoogleTest Adapter is installed, unittests can be viewed in a tree graph as well

   ![Alt text](/doc/screenshot.jpg?raw=true "Optional Title")

## Todos

 - Integrate with Circleci
 - Make it running under GNU/Linux
 
## References
- https://cognitivewaves.wordpress.com/cmake-and-visual-studio/#visual-studio-to-cmake-mapping

## License

MIT

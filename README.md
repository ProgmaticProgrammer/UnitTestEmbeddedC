# UnitTest EmbeddedC
![Alt text](/doc/screenshot.jpg?raw=true "Optional Title")

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

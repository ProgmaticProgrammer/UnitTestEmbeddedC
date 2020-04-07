cmake_minimum_required(VERSION 3.13)

# set the project name
project(UnitTestEmbeddedC VERSION 1.0)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_CONFIGURATION_TYPES Debug)

set(GMOCK_INC_DIR "./googletest/googlemock/include")
set(GTEST_INC_DIR "./googletest/googletest/include")

list(APPEND EXTRA_INCLUDES ${GMOCK_INC_DIR})                   
list(APPEND EXTRA_INCLUDES ${GTEST_INC_DIR})

#set( gtest_disable_pthreads ON )
set( gtest_force_shared_crt ON CACHE BOOL "Always use msvcrt.dll" FORCE)
add_subdirectory(googletest)

file(GLOB SOURCES "test/Main.cpp" "test/UnitTestFiles/*.cpp" "test/MockFiles/*.cpp" "src/CFiles/*.c")
add_executable(UnitTestEmbeddedC ${SOURCES})
set_property(TARGET UnitTestEmbeddedC PROPERTY
  MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
  
list(APPEND EXTRA_LIBS ${PROJECT_BINARY_DIR}/lib)

target_link_directories(UnitTestEmbeddedC PUBLIC ${EXTRA_LIBS} )	
target_link_libraries(UnitTestEmbeddedC PUBLIC gtest gmock)

add_dependencies(UnitTestEmbeddedC gtest gmock)

target_include_directories(UnitTestEmbeddedC PUBLIC
                           ./src
                           ./test
                           ./test/UnitTestFiles
                           ./test/MockFiles
                           ${EXTRA_INCLUDES}
                           )

                           
enable_testing()

# does the application run
add_test(NAME Runs COMMAND UnitTestEmbeddedC)


# TODO 1: Set the minimum required version of CMake to be 3.10
# DOCUMENTATION: https://cmake.org/cmake/help/latest/command/cmake_minimum_required.html#command:cmake_minimum_required
cmake_minimum_required(VERSION 3.10) # Specifies the min CMake version needed to build the executable 

# TODO 2: Create a project named Tutorial
# DOCUMENTATION: https://cmake.org/cmake/help/latest/command/project.html#command:project

# TODO 7: Set the project version number as 1.0 in the above project command
project(Tutorial VERSION 1.0)


# TODO 6: Set the variable CMAKE_CXX_STANDARD to 11
#         and the variable CMAKE_CXX_STANDARD_REQUIRED to True
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED True)

# TODO 8: Use configure_file to configure and copy TutorialConfig.h.in to
#         TutorialConfig.h

configure_file(TutorialConfig.h.in TutorialConfig.h)

# TODO 3: Add an executable called Tutorial to the project
# DOCUMENTATION: https://cmake.org/cmake/help/latest/command/add_executable.html#command:add_executable
# Hint: Be sure to specify the source file as tutorial.cxx
add_executable(Tutorial tutorial.cxx)

# TODO 9: Use target_include_directories to include ${PROJECT_BINARY_DIR}

target_include_directories(Tutorial PUBLIC "${PROJECT_BINARY_DIR}")
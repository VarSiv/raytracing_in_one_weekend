
# Minimum CMake version required
cmake_minimum_required(VERSION 3.16)

# Project name and version
project(Raytracer  VERSION 1.0 LANGUAGES CXX)

# Set the C++ standard

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add the executable (replace 'main.cpp' with your source files)
add_executable(MyExecutable
    main.cpp
)

# Include directories (if needed)
target_include_directories(MyExecutable PRIVATE
    include
)

# Link libraries (if needed, e.g., Boost, OpenCV, etc.)
# find_package(SomeLibrary REQUIRED)
# target_link_libraries(MyExecutable PRIVATE SomeLibrary::SomeLibrary)

# Add options for building (optional)
option(ENABLE_TESTS "Enable building tests" OFF)
if(ENABLE_TESTS)
    enable_testing()
    add_subdirectory(tests)
endif()

# Installation (optional)
install(TARGETS MyExecutable DESTINATION bin)

cmake_minimum_required(VERSION 3.0 FATAL_ERROR)

project(mmap_gfortran)
enable_language(Fortran)


# Define the executable name
SET(EXEC mmap_gfortran)

# we default to Release build type
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release")
endif()

SET(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/Modules/")


# Add our local modules to the module path
SET( FC "gfortran" )
SET(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/Modules/")

############################################################
# Define the actual files and folders that make up the build
############################################################

# Define the executable name
SET(EXECNAME mmap_fortran18)

# Define some directories
SET(SRC ${CMAKE_SOURCE_DIR}/src)
SET(BIN ${CMAKE_SOURCE_DIR}/bin)

# The source for the FOO binary and have it placed in the bin folder
ADD_SUBDIRECTORY(${SRC} ${BIN})

# Add a distclean target to the Makefile
ADD_CUSTOM_TARGET(distclean 
    COMMAND ${CMAKE_COMMAND} -P ${CMAKE_SOURCE_DIR}/distclean.cmake
)
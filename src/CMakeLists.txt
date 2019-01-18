########################################
# Set up how to compile the source files
########################################

# Add the source files
SET(EXEC_src ${SRC}/mmap_fortran18.f90
)

# Define the executable in terms of the source files
ADD_EXECUTABLE(${EXECNAME} ${EXEC_src})

#####################################
# Tell how to install this executable
#####################################

IF(WIN32)
    SET(CMAKE_INSTALL_PREFIX "C:\\Program Files")
ELSE()
    SET(CMAKE_INSTALL_PREFIX /usr/local)
ENDIF(WIN32)
INSTALL(TARGETS ${EXECNAME} RUNTIME DESTINATION bin)

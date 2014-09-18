include(${CMAKE_HOME_DIRECTORY}/biicode.cmake)

# Initializes block variables
INIT_BIICODE_BLOCK()

# Create config.h
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/config.h.in ${CMAKE_CURRENT_BINARY_DIR}/config.h)

# Add targets for the snappy library
add_library( snappy STATIC snappy.cc snappy-sinksource.cc snappy-stubs-internal.cc )

# Remove all binaries, tests do not work right now
IF (BII_BLOCK_EXES)
    SET(BII_BLOCK_EXES  )
ENDIF()

ADD_BIICODE_TARGETS()

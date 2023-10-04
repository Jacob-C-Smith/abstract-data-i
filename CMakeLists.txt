# Need CMake 3.20
cmake_minimum_required (VERSION 3.20)

# This is the name of the repository
project ("Abstract Data I")

# Set the correct paths
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/build)
set(CMAKE_PREFIX_PATH ${CMAKE_SOURCE_DIR}/extern/)

# Comment out for Debug mode
set(IS_DEBUG_BUILD CMAKE_BUILD_TYPE STREQUAL "Debug")

# Set for debug mode
if (${IS_DEBUG_BUILD})
    add_compile_definitions(NDEBUG)
endif ()

# Find the array module
if ( NOT "${HAS_ARRAY}")

    # Log
    message("[Abstract Data I] Adding array project")

    # Add the array directory
    add_subdirectory(${CMAKE_SOURCE_DIR}/extern/array ${CMAKE_SOURCE_DIR}/build/array)

    # Let any parent project know that this project has array
    set(HAS_ARRAY true PARENT_SCOPE)
endif()

# Find the dict module
if ( NOT "${HAS_DICT}")

    # Log
    message("[Abstract Data I] Adding dict project")

    # Add the dict directory
    add_subdirectory(${CMAKE_SOURCE_DIR}/extern/dict ${CMAKE_SOURCE_DIR}/build/dict)

    # Let any parent project know that this project has dict
    set(HAS_DICT true PARENT_SCOPE)
endif()

# Find the queue module
if ( NOT "${HAS_QUEUE}")

    # Log
    message("[Abstract Data I] Adding queue project")

    # Add the queue directory
    add_subdirectory(${CMAKE_SOURCE_DIR}/extern/queue ${CMAKE_SOURCE_DIR}/build/queue)

    # Let any parent project know that this project has queue
    set(HAS_QUEUE true PARENT_SCOPE)
endif()

# Find the set module
if ( NOT "${HAS_SET}")

    # Log
    message("[Abstract Data I] Adding set project")

    # Add the set directory
    add_subdirectory(${CMAKE_SOURCE_DIR}/extern/set ${CMAKE_SOURCE_DIR}/build/set)

    # Let any parent project know that this project has set
    set(HAS_SET true PARENT_SCOPE)
endif()

# Find the stack module
if ( NOT "${HAS_STACK}")

    # Log
    message("[Abstract Data I] Adding stack project")

    # Add the stack directory
    add_subdirectory(${CMAKE_SOURCE_DIR}/extern/stack ${CMAKE_SOURCE_DIR}/build/stack)

    # Let any parent project know that this project has stack
    set(HAS_STACK true PARENT_SCOPE)
endif()

# Find the tuple module
if ( NOT "${HAS_TUPLE}")

    # Log
    message("[Abstract Data I] Adding tuple project")

    # Add the tuple directory
    add_subdirectory(${CMAKE_SOURCE_DIR}/extern/tuple ${CMAKE_SOURCE_DIR}/build/tuple)

    # Let any parent project know that this project has tuple
    set(HAS_TUPLE true PARENT_SCOPE)
endif()

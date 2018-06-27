# build shared library
add_library(add SHARED add.cpp)
# set the version for shared library
SET_TARGET_PROPERTIES(add PROPERTIES VERSION 1.2 SOVERSION 1)

#build static library
add_library(add_static STATIC add.cpp)

# install the shared library ${CMAKE_INSTALL_PREFIX}/libs
install(TARGETS add
    LIBRARY DESTINATION libs)

# install the static library ${CMAKE_INSTALL_PREFIX}/libs
install(TARGETS add_static
    ARCHIVE DESTINATION libs)

MESSAGE("test/libs CMAKE_CURRENT_SOURCE_DIR " ${CMAKE_CURRENT_SOURCE_DIR})
MESSAGE("test/libs project source dir " ${PROJECT_SOURCE_DIR})
MESSAGE("test/libs PROJECT_SOURCE_DIR " ${PROJECT_BINARY_DIR})
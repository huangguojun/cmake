cmake_minimum_required(VERSION 2.6)

# set project name from current directory
get_filename_component(BASENAME ${CMAKE_SOURCE_DIR} NAME)
project(${BASENAME})


set(CMAKE_BUILD_TYPE DEBUG)
set(CMAKE_C_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS "-Wall")



# define executable to build
include_directories("inc")
aux_source_directory(src SRC_FILES)
add_executable(${PROJECT_NAME} ${SRC_FILES})

# add sub

# package
install (TARGETS ${PROJECT_NAME} DESTINATION bin)

SET(CPACK_GENERATOR "DEB")
SET(CPACK_DEBIAN_PACKAGE_MAINTAINER "Michel Promonet") 
SET(CPACK_PACKAGE_CONTACT "michel.promonet@free.fr") 
SET(CPACK_SYSTEM_NAME ${CMAKE_SYSTEM_NAME}-${CMAKE_SYSTEM_PROCESSOR})
INCLUDE(CPack)


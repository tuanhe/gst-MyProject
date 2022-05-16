cmake_minimum_required (VERSION 3.10.0)

IF (CONFIG STREQUAL YES)
    ADD_DEFINITIONS(-DHAVE_CONFIG_H)
ENDIF()

project (gstmyproject)

find_package(PkgConfig REQUIRED)
pkg_search_module(GST REQUIRED gstreamer-1.0 gstreamer-base-1.0)
include_directories(${GST_INCLUDE_DIRS})
link_directories(${GST_LIBRARIES})
MESSAGE(STATUS "gstreamer include dirs:" ${GST_INCLUDE_DIRS})
MESSAGE(STATUS "gstreamer lib:" ${GST_LIBRARIES})

find_package(PkgConfig REQUIRED)
pkg_search_module(GSTBASE REQUIRED gstreamer-base-1.0)
MESSAGE(STATUS "gstreamerbase include dirs:" ${GSTBASE_INCLUDE_DIRS})
MESSAGE(STATUS "gstreamerbase lib:" ${GSTBASE_LIBRARIES})

add_subdirectory (apps)
add_subdirectory (plugins)
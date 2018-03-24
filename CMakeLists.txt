# CMake Build File - GA teaching example

cmake_minimum_required (VERSION 2.6)
cmake_policy(SET CMP0037 OLD)
set( CMAKE_CXX_FLAGS "-O3 -Wall ${CMAKE_CXX_FLAGS}" )
# linux specific stuff

IF ( UNIX )
   set( CMAKE_PREFIX_PATH "/opt/opencv" )
   set_property(GLOBAL PROPERTY TARGET_SUPPORTS_SHARED_LIBS TRUE)
   MESSAGE( "LINUX CONFIG" )
ENDIF ( UNIX )

# windows (inc. 64-bit specific stuff)

IF ( WIN32 )
   set( CMAKE_PREFIX_PATH "C:/OpenCV/build" )
   set( OpenCV_DIR "C:/OpenCV/build" )
   MESSAGE( "WINDOWS CONFIG" )
ENDIF ( WIN32 )

find_package( OpenCV REQUIRED )
# MESSAGE ( "OPENCV CONFIG" )
# MESSAGE ( ${OpenCV_LIBS} )

project(ga)
add_executable(correlation_ga ga_interface.cpp)
target_link_libraries(correlation_ga ${OpenCV_LIBS} )

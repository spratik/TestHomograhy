cmake_minimum_required(VERSION 2.8)

PROJECT (TestHomography)

find_package(OpenCV  REQUIRED)


file(GLOB TestHomography_SRCS
    "*.h"
    "*.cpp")
ADD_EXECUTABLE (TestHomography ${TestHomography_SRCS})



if (OpenCV_FOUND)
	include_directories( ${OpenCV_INCLUDE_DIRS} )
#	include_directories("${OPENCV_CONFIG_PATH}/include")
	target_link_libraries( TestHomography ${OpenCV_LIBS} )
else (OpenCV_FOUND)
message("PB->OPENCV = ${OpenCV_INCLUDE_DIRS}")
endif (OpenCV_FOUND)


cmake_minimum_required(VERSION 3.4.1)

add_library(
        native-lib
        SHARED
        native-lib.cpp)

include_directories(include)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -L${CMAKE_SOURCE_DIR}/../../../libs/${CMAKE_ANDROID_ARCH_ABI}")

find_library(
        log-lib
        log)

target_link_libraries(
        native-lib
        avformat avcodec avfilter avutil swresample swscale
        ${log-lib})


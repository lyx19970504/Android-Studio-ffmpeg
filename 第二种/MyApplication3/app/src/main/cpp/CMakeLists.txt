cmake_minimum_required(VERSION 3.4.1)

include_directories(include)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -L${CMAKE_SOURCE_DIR}/../jniLibs/${CMAKE_ANDROID_ARCH_ABI}")
add_library(
        native-lib
        SHARED
        native-lib.cpp)


find_library(
        log-lib
        log)

target_link_libraries(
        native-lib
        avformat avcodec avfilter avutil swresample swscale
        ${log-lib})
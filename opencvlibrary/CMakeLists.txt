cmake_minimum_required(VERSION 3.4.1)

#设置生成的so动态库最后输出的路径
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/jniLibs/${ANDROID_ABI})

set(ROOT_PATH ${CMAKE_SOURCE_DIR}/native)
#set(3RD_PARTY_LIBS ${ROOT_PATH}/3rdparty/libs)
#set(HEADER_PATH ${ROOT_PATH}/jni/include)
#set(LIBS ${ROOT_PATH}/libs)

#file(GLOB 3rdStaticLibs "${3RD_PARTY_LIBS}/${ANDROID_ABI}/*.a")
#add_library(3rdStaticLib STATIC IMPORTED)
#set_target_properties(3rdStaticLib PROPERTIES IMPORTED_LOCATION
    #"${3RD_PARTY_LIBS}/${ANDROID_ABI}/libcpufeatures.a"
    #"${3RD_PARTY_LIBS}/${ANDROID_ABI}/libIlmImf.a"
    #"${3RD_PARTY_LIBS}/${ANDROID_ABI}/liblibjasper.a"
    #"${3RD_PARTY_LIBS}/${ANDROID_ABI}/liblibjpeg.a"
    #"${3RD_PARTY_LIBS}/${ANDROID_ABI}/liblibpng.a"
    #"${3RD_PARTY_LIBS}/${ANDROID_ABI}/liblibtiff.a"
    #"${3RD_PARTY_LIBS}/${ANDROID_ABI}/liblibwebp.a"
    #"${3RD_PARTY_LIBS}/${ANDROID_ABI}/libtbb.a"
    #"${3RD_PARTY_LIBS}/${ANDROID_ABI}/libtegra_hal.a")

#add_library(protobuf STATIC IMPORTED)
#set_target_properties(protobuf PROPERTIES IMPORTED_LOCATION
    #"${3RD_PARTY_LIBS}/${ANDROID_ABI}/liblibprotobuf.a")


add_library(
             opencv3.3
             SHARED
             ${ROOT_PATH}/native-lib.cpp)
find_library(
              log-lib
              log )
target_link_libraries(
                       opencv3.3
                       #3rdStaticLib
                       #protobuf
                       ${log-lib} )
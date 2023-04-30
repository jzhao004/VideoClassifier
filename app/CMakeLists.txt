cmake_minimum_required(VERSION 3.4.1)
project(videoclassification) # set project name
set(CMAKE_CXX_STANDARD 14) # specify c++ standard

add_library(videoclassification SHARED src/main/cpp/videoclassification.cpp)

file(GLOB PYTORCH_INCLUDE_DIRS "$libs/pytorch_android*.aar/headers")
file(GLOB PYTORCH_LINK_DIRS "$libs/pytorch_android*.aar/jni/${ANDROID_ABI}")

target_compile_options(videoclassification PRIVATE -fexceptions)

find_library(PYTORCH_LIBRARY pytorch_jni PATHS ${PYTORCH_LINK_DIRS})
find_library(FBIJNI_LIBRARY fbjni PATHS ${PYTORCH_LINK_DIRS})

set(OPENCV_INCLUDE_DIR "OpenCV-android-sdk/sdk/native/jni/include")
target_include_directories(videoclassification PRIVATE  "${OPENCV_INCLUDE_DIR}" ${PYTORCH_INCLUDE_DIRS})

set(OPENCV_LIB_DIR "OpenCV-android-sdk/sdk/native/libs/${ANDROID_ABI}")

find_library(OPENCV_LIBRARY opencv_java4 PATHS ${OPENCV_LIB_DIR} NO_CMAKE_FIND_ROOT_PATH)

target_link_libraries(videoclassification
        ${PYTORCH_LIBRARY}
        ${FBJNI_LIBRARY}
        ${OPENCV_LIBRARY}
        log)


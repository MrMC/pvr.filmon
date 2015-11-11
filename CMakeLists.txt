project(pvr.filmon)

cmake_minimum_required(VERSION 2.6)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(mrmc REQUIRED)
find_package(mrmcplatform REQUIRED)
find_package(platform REQUIRED)
find_package(JsonCpp REQUIRED)

include_directories(${mrmcplatform_INCLUDE_DIRS}
                    ${platform_INCLUDE_DIRS}
                    ${JSONCPP_INCLUDE_DIRS}
                    ${MRMC_INCLUDE_DIR})

set(DEPLIBS ${platform_LIBRARIES} ${JSONCPP_LIBRARIES})

set(FILMON_SOURCES src/client.cpp
                   src/FilmonAPI.cpp
                   src/PVRFilmonData.cpp
                   src/md5.cpp)

build_addon(pvr.filmon FILMON DEPLIBS)

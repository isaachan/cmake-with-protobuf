CMAKE_MINIMUM_REQUIRED(VERSION 3.22.1)
PROJECT(ChangeDependencies)

INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR})

ADD_LIBRARY(Math2Static STATIC math2.cpp)
ADD_LIBRARY(Math2Shared SHARED math2.cpp)


ADD_LIBRARY(Math3Static_with_Math2Static STATIC math3.cpp)
ADD_LIBRARY(Math3Static_with_Math2Shared STATIC math3.cpp)

ADD_LIBRARY(Math3Shared_with_Math2Static SHARED math3.cpp)
ADD_LIBRARY(Math3Shared_with_Math2Shared SHARED math3.cpp)

TARGET_LINK_LIBRARIES(Math3Static_with_Math2Static Math2Static)
TARGET_LINK_LIBRARIES(Math3Static_with_Math2Shared Math2Shared)
TARGET_LINK_LIBRARIES(Math3Shared_with_Math2Static Math2Static)
TARGET_LINK_LIBRARIES(Math3Shared_with_Math2Shared Math2Shared)
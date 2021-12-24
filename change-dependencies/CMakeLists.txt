cmake_minimum_required(3.22.1)
project(ChangeDependencies)

INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR})

ADD_LIBRARY(Math2Static STATIC math2.cpp)
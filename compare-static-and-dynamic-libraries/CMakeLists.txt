project(StaticAndDynamicLibrary)
cmake_minimum_required(VERSION 3.22.1)

INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR})

# Use same source code to build a static library and a shared library.
# Then compare the executable applications that using these two libraries.

# Create static library.
Add_Library(Add_Static STATIC math2.cpp)
Add_Executable(Hello_Main_From_Static main.cc)
Target_Link_Libraries(Hello_Main_From_Static Add_Static)

# Create shared library.
Add_Library(Add_Shared SHARED math2.cpp)
Add_Executable(Hello_Main_From_Shared main.cc)
Target_Link_Libraries(Hello_Main_From_Shared Add_Shared)

cmake_minimum_required(VERSION 3.25)

project (CPPCartoon)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

find_package(OpenMP)
  
add_executable (cppCartoon
  cpdb/utils.cpp
  cpdb/cpdb.cpp
  #matrix.cpp
  main.cpp
  cartoon.cpp
  )

if(OpenMP_CXX_FOUND)
  target_link_libraries(cppCartoon PUBLIC OpenMP::OpenMP_CXX)
  add_definition(-DUSEOMP=1)
endif()

cmake_minimum_required(VERSION 3.25)

project (CPPCartoon)

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
endif()

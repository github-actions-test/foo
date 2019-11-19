cmake_minimum_required(VERSION 3.0)
project(foo VERSION 1.0.0 DESCRIPTION "the almighty foo library")
add_library(foo SHARED foo.cpp)
set_target_properties(foo PROPERTIES VERSION ${PROJECT_VERSION})
set_target_properties(foo PROPERTIES SOVERSION 1)
set_target_properties(foo PROPERTIES PUBLIC_HEADER foo.hpp)

include(GNUInstallDirs)
install(TARGETS foo
  LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
  PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})


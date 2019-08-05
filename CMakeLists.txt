cmake_minimum_required(VERSION 3.5)
project(P3)


set (CMAKE_MODULE_PATH "${CMAKE_MODULE_PATH};${CMAKE_CURRENT_SOURCE_DIR}/cmake")


find_package(xtl REQUIRED)
message(STATUS "Found xtl: ${xtl_INCLUDE_DIRS}/xtl")
find_package(xtensor-python)
message(STATUS "Found xtensor-python: ${xtensor-python_INCLUDE_DIRS}/xtensor-python")
find_package(xtensor REQUIRED)
message(STATUS "Found xtensor: ${xtensor_INCLUDE_DIRS}/xtensor")
find_package(pybind11 REQUIRED)
message(STATUS "Found pybind11: ${pybind11_INCLUDE_DIRS}/pybind11")
find_package(NumPy REQUIRED)
message(STATUS "Found numpy: ${NUMPY_INCLUDE_DIRS}")




pybind11_add_module(xtensor_python_test example.cpp)

include_directories(
${xtl_INCLUDE_DIRS}
${xtensor_INCLUDE_DIRS}
${xtensor-python_INCLUDE_DIRS}
${NUMPY_INCLUDE_DIRS}
${pybind11_INCLUDE_DIRS}
)
set(LIBS ${LIBS} ${xtensor-python_LIBRARIES})


target_link_libraries(xtensor_python_test ${LIBS})

get_property(dirs DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY INCLUDE_DIRECTORIES)
foreach(dir ${dirs})
  message(STATUS "dir='${dir}'")
endforeach()

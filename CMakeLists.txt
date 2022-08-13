cmake_minimum_required(VERSION 3.14)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(dlib-playground)

find_package(dlib 19.24.0 REQUIRED PATHS "${DLIB_ROOT}")
if (dlib_FOUND)
    message("dlib found")
else (dlib_FOUND)
    message("dlib not found")
endif()

SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -static")

add_executable(${PROJECT_NAME} 
    "src/main.cpp"
)

target_link_libraries(${PROJECT_NAME} dlib::dlib)
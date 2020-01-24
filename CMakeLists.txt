cmake_minimum_required(VERSION 3.13)
set(PROJECT_NAME Asteroids)
project(${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 17)
set(SOURCE_FILES main.cpp)
add_executable(${PROJECT_NAME} main.cpp)

target_compile_features(${PROJECT_NAME} PUBLIC cxx_std_17)

set(SFML_ROOT "C:/Users/fools/Documents/Libs/SFML-2.5.1V64/")

set(SFML_STATIC_LIBRARIES FALSE)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")
find_package(SFML 2 REQUIRED COMPONENTS system window graphics network audio)
if(SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(${PROJECT_NAME} ${SFML_LIBRARIES})
endif()
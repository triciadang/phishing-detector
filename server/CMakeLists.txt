cmake_minimum_required (VERSION 3.10)
project (PhishDetector)
set(NAME "PhishDetector")

add_definitions(-Wfatal-errors)

set(CMAKE_CXX_STANDARD 11)
set(sources src/main.cpp src/PhishDetector.cpp src/PhishDatabase.cpp src/PictureExtractor.cpp src/SourceFinder.cpp src/WhoIS.cpp)

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -pthread")

add_executable(${NAME} ${sources})

target_link_libraries(${NAME} curl)
target_link_libraries(${NAME} jsoncpp)
target_link_libraries(${NAME} boost_system)

cmake_minimum_required(VERSION 3.10)

# Tên project
project(SnakeGame)

# Các file header và source
set(SOURCE_FILES 
    src/main.cpp 
    src/controller.cpp 
    src/game.cpp 
    src/renderer.cpp 
    src/snake.cpp 
    src/scoremanager.cpp)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(SnakeGame ${SOURCE_FILES})

find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})
string(STRIP ${SDL2_LIBRARIES} SDL2_LIBRARIES)
target_link_libraries(SnakeGame ${SDL2_LIBRARIES})
cmake_minimum_required(VERSION 3.16)

project(ProcessLab LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 98)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Собираем process.cpp в отдельную статическую библиотеку
add_library(process STATIC process.cpp)

add_executable(process_test main.cpp)

# Подключаем библиотеку к тестовой программе
target_link_libraries(process_test PRIVATE process)

# Отдельная дочерняя программа, которую будет запускать тестовая утилита
add_executable(child child.cpp)

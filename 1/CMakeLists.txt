cmake_minimum_required(VERSION 3.16) # CMake версии 3.16 или новее

project(HelloWorld LANGUAGES CXX) #  объявляет проект:
# - HelloWorld - его название;
# - LANGUAGES - далее перечисляются языки проекта
# - CXX - обозначение языка C++ в CMake

set(CMAKE_CXX_STANDARD 98) # собирать программу с использованием стандарта C++98
set(CMAKE_CXX_STANDARD_REQUIRED ON) # делает выбранный стандарт обязательным
set(CMAKE_CXX_EXTENSIONS OFF) # в разных компилятораз могут быть расширения, которых нет в стандартном c++ 98 . это отключает все такие приколы

add_executable(hello main.cpp) # нужно создать исполняемую программу с именем hello из файла main.cpp. На Windows результатом будет hello.exe, а в Ubuntu - обычно hello, без расширения .exe
# HelloWorld - название всего проекта, а hello - название создаваемой программы. Они могут отличаться

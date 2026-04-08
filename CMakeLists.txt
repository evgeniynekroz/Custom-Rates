cmake_minimum_required(VERSION 3.16)
project(custom-rates VERSION 1.0.0)

# Если эта строка падает, значит Geode CLI не прописал пути в окружение
find_package(Geode REQUIRED)

add_library(${PROJECT_NAME} SHARED src/main.cpp)

setup_geode_mod(${PROJECT_NAME})

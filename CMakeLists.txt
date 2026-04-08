cmake_minimum_required(VERSION 3.16)

project(custom-rates VERSION 1.0.0)

# Принудительно ищем Geode там, куда его ставит GitHub Action
if(NOT Geode_FOUND)
    # Путь для Windows
    list(APPEND CMAKE_PREFIX_PATH "C:/Users/runneradmin/AppData/Local/Geode/sdk")
    # Путь для Linux/Android
    list(APPEND CMAKE_PREFIX_PATH "${CMAKE_CURRENT_BINARY_PATH}/geode-sdk")
    list(APPEND CMAKE_PREFIX_PATH "$ENV{GEODE_SDK}")
endif()

find_package(Geode REQUIRED)

add_library(${PROJECT_NAME} SHARED
    src/main.cpp
)

setup_geode_mod(${PROJECT_NAME})

cmake_minimum_required(VERSION 3.16)

# Название проекта СТРОГО совпадает с ID из mod.json
project(custom-rates VERSION 1.0.0)

# Принудительно указываем путь к Geode SDK для GitHub Actions
if(DEFINED ENV{GEODE_SDK})
    set(Geode_DIR "$ENV{GEODE_SDK}")
    list(APPEND CMAKE_PREFIX_PATH "$ENV{GEODE_SDK}")
endif()

find_package(Geode REQUIRED)

add_library(${PROJECT_NAME} SHARED
    src/main.cpp
)

setup_geode_mod(${PROJECT_NAME})

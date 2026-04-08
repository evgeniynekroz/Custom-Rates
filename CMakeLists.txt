cmake_minimum_required(VERSION 3.25)

project(CustomRates VERSION 1.0.0)

find_package(Geode REQUIRED)

add_geode_mod(
    ${PROJECT_NAME}
    SOURCES 
        src/main.cpp
)

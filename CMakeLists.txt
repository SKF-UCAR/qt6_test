cmake_minimum_required(VERSION 3.18)

# Project name and setting C++ version
project(qt6_test LANGUAGES CXX)

# Set the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Find the required Qt6 components
find_package(Qt6 REQUIRED COMPONENTS Widgets)

# Add UI files, headers, and sources
set(CMAKE_AUTOMOC ON)   # Enable automatic MOC (Meta Object Compiler) for Qt
set(CMAKE_AUTORCC ON)   # Enable automatic RCC (Resource Compiler) if you have Qt resource files
set(CMAKE_AUTOUIC ON)   # Enable automatic UIC for .ui files

# Add the sources and UI files
set(SOURCES
    main.cpp
    mainwindow.cpp
    dialog.cpp
)

set(HEADERS
    mainwindow.h
    dialog.h
)

set(UIS
    mainwindow.ui
    dialog.ui
)

# Create the executable
add_executable(${PROJECT_NAME} ${SOURCES} ${UIS} ${HEADERS})

# Link the Qt6 Widgets module
target_link_libraries(${PROJECT_NAME} Qt6::Widgets)

# Generated from hellovulkanwindow.pro.

cmake_minimum_required(VERSION 3.14)
project(hellovulkanwindow LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

set(INSTALL_EXAMPLEDIR "examples")

find_package(Qt6 COMPONENTS Core)
find_package(Qt6 COMPONENTS Gui)

add_qt_gui_executable(hellovulkanwindow
    hellovulkanwindow.cpp hellovulkanwindow.h
    main.cpp
)
target_link_libraries(hellovulkanwindow PUBLIC
    Qt::Core
    Qt::Gui
)

install(TARGETS hellovulkanwindow
    RUNTIME DESTINATION "${INSTALL_EXAMPLEDIR}"
    BUNDLE DESTINATION "${INSTALL_EXAMPLEDIR}"
    LIBRARY DESTINATION "${INSTALL_EXAMPLEDIR}"
)

cmake_minimum_required(VERSION 3.13)
project(BuildWithCLion)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_PREFIX_PATH "/usr/lib/x86_64-linux-gnu/cmake/Qt5")

find_package(Qt5Core REQUIRED)
find_package(Qt5Gui REQUIRED)
find_package(Qt5PrintSupport REQUIRED)
find_package(Qt5Widgets REQUIRED)

include_directories(
        ${Qt5Widgets_INCLUDE_DIRS}
        ${Qt5Gui_INCLUDE_DIRS}
        ${Qt5Core_INCLUDE_DIRS}
        ${Qt5PrintSupport_INCLUDE_DIRS}
)

add_executable(BuildWithCLion main.cpp mainwindow.cpp qcustomplot.cpp axistag.cpp)
target_link_libraries(BuildWithCLion Qt5::Core Qt5::Widgets Qt5::Gui Qt5::PrintSupport)

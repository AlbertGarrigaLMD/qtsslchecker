cmake_minimum_required(VERSION 3.18)
project(qtsslcheck)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt5 REQUIRED
    Core
    Widgets
    Svg
    Network
    Concurrent
    Sql
)

find_package(OpenSSL REQUIRED)

add_executable(
    qtsslcheck
	main.cpp
)

target_link_libraries(
    qtsslcheck
    PUBLIC
	Qt5::Core
	Qt5::Widgets
	Qt5::Svg
	Qt5::Network
	Qt5::Concurrent
	OpenSSL::SSL
)

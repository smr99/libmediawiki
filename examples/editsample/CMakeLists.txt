#
# Copyright (c) 2010-2014, Gilles Caulier, <caulier dot gilles at gmail dot com>
#
# Redistribution and use is allowed according to the terms of the BSD license.
# For details see the accompanying COPYING-CMAKE-SCRIPTS file.

cmake_minimum_required(VERSION 2.8.12)

project(EditSample)

find_package(Qt5 5.2.0 NO_MODULE REQUIRED Core Network Widgets)
find_package(KF5MediaWiki ${KF5_VERSION} REQUIRED)
find_package(KF5CoreAddons ${KF5_VERSION} REQUIRED NO_MODULE)

set(CMAKE_AUTOMOC ON)

add_executable(
    EditSample
    main.cpp
    mainwindow.cpp
)

target_link_libraries(EditSample
    PRIVATE
        Qt5::Core
        Qt5::Network
        Qt5::Widgets
        KF5::MediaWiki
        KF5::CoreAddons
)
set_target_properties(EditSample PROPERTIES COMPILE_FLAGS "-std=c++11")

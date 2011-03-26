# Copyright (C) 2007-2009 LuaDist.
# Created by Peter Drahoš
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

PROJECT (luacurl C)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
INCLUDE(dist.cmake)

# Find curl
FIND_PACKAGE(CURL REQUIRED)
INCLUDE_DIRECTORIES(${CURL_INCLUDE_DIR})

ADD_LUA_MODULE(luacurl luacurl.c luacurl.def)
TARGET_LINK_LIBRARIES(luacurl ${CURL_LIBRARY})

INSTALL (TARGETS luacurl DESTINATION ${INSTALL_CMOD})

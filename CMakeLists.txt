# Copyright (C) 2007-2012 LuaDist.
# Created by Peter Drahoš
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( luacurl C )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )
include ( lua )

# Find curl
find_package ( CURL REQUIRED )
include_directories ( ${CURL_INCLUDE_DIR} )

install_lua_module ( luacurl luacurl.c luacurl.def LINK ${CURL_LIBRARY} )

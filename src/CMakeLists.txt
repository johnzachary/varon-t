# -*- coding: utf-8 -*-
# ----------------------------------------------------------------------
# Copyright © 2012-2015, RedJack, LLC.
# All rights reserved.
#
# Please see the COPYING file in this distribution for license details.
# ----------------------------------------------------------------------


# Update the VERSION_INFO property below according to the following rules (taken
# from [1]):
#
# VERSION_INFO = current:revision:age
#
#   1. Start with a VERSION of `0:0:0` for each shared library.
#   2. Update VERSION_INFO only immediately before a public release of your
#      software.  More frequent updates are unnecessary, and only guarantee that
#      the current interface number gets larger faster.
#   3. If the library source code has changed at all since the last update, then
#      increment `revision` (`c:r:a` becomes `c:r+1:a`).
#   4. If any interfaces have been added, removed, or changed since the last
#      update, increment `current`, and set `revision` to 0.
#   5. If any interfaces have been added since the last public release, then
#      increment `age`.
#   6. If any interfaces have been removed or changed since the last public
#      release, then set `age` to 0.
#
# Note that changing `current` and setting `age` to 0 means that you are
# releasing a new backwards-incompatible version of the library.  This has
# implications on packaging, so once an API has stabilized, this should be a
# rare occurrence.
#
# [1] http://www.gnu.org/software/libtool/manual/html_node/Updating-version-info.html#Updating-version-info

add_c_library(
    libvrt
    OUTPUT_NAME vrt
    PKGCONFIG_NAME varon-t
    VERSION_INFO 2:0:0
    SOURCES
        libvrt/queue.c
        libvrt/yield.c
    LIBRARIES
        threads
        libcork
        clogger
        bowsprit
)

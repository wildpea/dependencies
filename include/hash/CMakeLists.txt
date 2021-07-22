cmake_minimum_required (VERSION 3.4)

set(TARGET MurmurHash3)
project (${TARGET})

set(SERVERS_ROOT $ENV{SERVERS_ROOT})

include_directories(
    /usr/local/include/
)

link_directories(
    /usr/local/lib
)

# 指定生成目标

aux_source_directory(. DIR_SRCS)

add_compile_options(-g -std=c++0x -Wall -fPIC)

add_library(${TARGET} SHARED ${DIR_SRCS})

#set_target_properties(${TARGET} PROPERTIES ARCHIVE_OUTPUT_DIRECTORY "${SERVERS_ROOT}/dependencies/lib")

#TARGET_LINK_LIBRARIES(
    #${TARGET}
    #libgtest.a
    #libgflags.a
    #libglog.a
#)

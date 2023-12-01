cmake_minimum_required(VERSION 3.0)
project(DBus_C)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/build)

include_directories(${CMAKE_SOURCE_DIR})

add_executable(sender
    signalSender.c
)

add_executable(listener
    signalListener.c
)


target_link_libraries(receiver systemd)

install(TARGETS receiver DESTINATION ${CMAKE_INSTALL_BINDIR})
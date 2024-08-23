cmake_minimum_required(VERSION 3.16)

project(Coral.Native
LANGUAGE CXX
)
add_library(Coral.Native STATIC)

target_include_directories(Coral.Native PUBLIC Include/Coral)

file(GLOB CORAL_NATIVE_SOURCES CONFIGURE_DEPENDS RELATIVE Source/Coral *cpp *hpp *h)
file(GLOB CORAL_NATIVE_HEADERS CONFIGURE_DEPENDS RELATIVE Include/Coral *cpp *hpp *h)
target_sources(Coral.Native PRIVATE ${CORAL_NATIVE_HEADERS} ${CORAL_NATIVE_SOURCES})

target_link_libraries(Coral.Native PUBLIC NetCore)
target_precompile_headers(Coral.Native PUBLIC Source/CoralPCH.hpp)
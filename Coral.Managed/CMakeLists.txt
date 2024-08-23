cmake_minimum_required(VERSION 3.16)

project(Coral.Managed
LANGUAGE CSharp 
)
add_library(Coral.Managed SHARED)
set_target_properties(Coral.Managed PROPERTIES
    LINKER_LANGUAGE CSharp
)
file(GLOB CORAL_MANAGED_SOURCES CONFIGURE_DEPENDS RELATIVE Source *cs)
target_sources(Coral.Managed PRIVATE ${CORAL_MANAGED_SOURCES})
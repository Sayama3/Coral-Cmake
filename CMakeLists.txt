cmake_minimum_required(VERSION 3.16)

project(Coral
    VERSION 0.0.1
    DESCRIPTION "Coral is a C++/C# wrapper around the .NET CoreCLR library, the purpose of Coral is to provide a native interface similar to Mono, but in a more modern style, and using .NET Core instead of .NET Framework"
    HOMEPAGE_URL "https://github.com/Sayama3/Coral-Cmake"
    LANGUAGES CSharp CXX
)

option(CORAL_COMPILE_EXAMPLE "Compile the examples" OFF)
option(CORAL_COMPILE_TESTS "Compile the tests" ON)

add_library(NetCore SHARED IMPORTED)
target_include_directories(NetCore ITNERFACE NetCore)

add_subdirectory(Coral.Managed)
add_subdirectory(Coral.Native)

if(CORAL_COMPILE_EXAMPLE)
    add_subdirectory(Example)
endif()

if(CORAL_COMPILE_TESTS)
    add_subdirectory(Tests)
endif()
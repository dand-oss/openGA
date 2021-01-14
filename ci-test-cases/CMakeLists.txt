cmake_minimum_required(VERSION 2.8)
project(
    "ci-test-cases"
    LANGUAGES CXX
    VERSION 7.1.0)

set(exename "Polyfit-Boost-demo")

include(GNUInstallDirs)

# use our own library - installed 
find_package(openGA CONFIG REQUIRED)

add_executable(${exename})
target_link_libraries(${exename} PUBLIC
    openGA::openGA
    )
target_sources(${exename} PRIVATE
    main.cpp
)

install(TARGETS ${exename}
    RUNTIME DESTINATION bin)

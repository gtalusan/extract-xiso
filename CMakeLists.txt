cmake_minimum_required(VERSION 3.0)
project(extract-xiso)

string(TOUPPER __${CMAKE_SYSTEM_NAME}__ TARGET_OS)

set(SOURCE_FILES
	extract-xiso.c
)

add_executable(extract-xiso ${SOURCE_FILES})
target_compile_definitions(extract-xiso PRIVATE ${TARGET_OS})
target_compile_options(extract-xiso PRIVATE -g -Og -Wall -Werror -pedantic)
install(TARGETS extract-xiso RUNTIME DESTINATION "${CMAKE_INSTALL_PREFIX}/bin")

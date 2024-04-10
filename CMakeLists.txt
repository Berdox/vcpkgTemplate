cmake_minimum_required(VERSION 3.10)

set(vcpkg "$ENV{VCPKG_ROOT}/scripts/buildsystems/vcpkg.cmake")
if(NOT CMAKE_TOOLCHAIN_FILE AND EXISTS "${vcpkg}")
  set(CMAKE_TOOLCHAIN_FILE "${vcpkg}"
      CACHE FILEPATH "CMake toolchain file")
  message(STATUS "vcpkg toolchain found: ${CMAKE_TOOLCHAIN_FILE}")
endif()

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project ("vcpkgTemplate")

# Add source to this project's executable.
add_executable (vcpkgTemplate "src/main.cpp" "include/example.hpp")

find_package(fmt CONFIG REQUIRED)

target_link_libraries(vcpkgTemplate PRIVATE fmt::fmt)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET vcpkgTemplate PROPERTY CXX_STANDARD 20) 
endif()

# TODO: Add tests and install targets if needed.

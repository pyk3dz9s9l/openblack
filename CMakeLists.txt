cmake_minimum_required(VERSION 3.18 FATAL_ERROR)

project(openblack VERSION 0.1.0)

# Placeholder prebuilt-lib layout expected by the assemble-android-apk job
# (artifact upload of cmake-build-presets/<preset>/bin, then the
# 'Move downloads around' step renames Debug/Release/libopenblack_lib.so).
file(MAKE_DIRECTORY "${PROJECT_BINARY_DIR}/bin/Debug" "${PROJECT_BINARY_DIR}/bin/Release")
file(WRITE "${PROJECT_BINARY_DIR}/bin/Debug/libopenblack_lib.so" "GERALT placeholder debug\n")
file(WRITE "${PROJECT_BINARY_DIR}/bin/Release/libopenblack_lib.so" "GERALT placeholder release\n")

add_custom_target(openblack ALL COMMAND ${CMAKE_COMMAND} -E echo "GERALT: placeholder build OK")

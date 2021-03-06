cmake_minimum_required(VERSION 3.0)
project(cmakeut VERSION 1.0.2)


set(CMAKE_VERBOSE_MAKEFILE ON)


list(APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake/")
include(CMakePackageConfigHelpers)
include(${PROJECT_SOURCE_DIR}/all.cmake)

set(CMAKEUT_INSTALL_PATH "${CMAKE_INSTALL_PREFIX}/share/cmakeut/")

configure_package_config_file(  "cmake/cmakeutConfig.cmake.in"
                                "${PROJECT_BINARY_DIR}/cmakeutConfig.cmake"
                                INSTALL_DESTINATION "${CMAKE_INSTALL_PREFIX}/share/cmakeut/"
                                NO_SET_AND_CHECK_MACRO
                                NO_CHECK_REQUIRED_COMPONENTS_MACRO)

write_basic_package_version_file(
    ${PROJECT_BINARY_DIR}/cmakeutConfigVersion.cmake
    VERSION ${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}.${PROJECT_VERSION_PATCH}
    COMPATIBILITY SameMajorVersion)


install (FILES "${PROJECT_BINARY_DIR}/cmakeutConfig.cmake"
         DESTINATION "${CMAKEUT_INSTALL_PATH}/")

install (FILES "${PROJECT_BINARY_DIR}/cmakeutConfigVersion.cmake"
         DESTINATION "${CMAKEUT_INSTALL_PATH}/")


install (DIRECTORY "${PROJECT_SOURCE_DIR}/cmake"
         DESTINATION "${CMAKEUT_INSTALL_PATH}"
         FILES_MATCHING PATTERN "*.cmake")

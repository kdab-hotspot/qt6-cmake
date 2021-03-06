cmake_minimum_required(VERSION 3.15.0)

# Run auto detection routines
include(${CMAKE_CURRENT_SOURCE_DIR}/cmake/QtAutoDetect.cmake)

project(QtBase
    VERSION 6.0.0
    DESCRIPTION "Qt Base Libraries"
    HOMEPAGE_URL "https://qt.io/"
    LANGUAGES CXX C ASM
)

## Add some paths to check for cmake modules:
list(PREPEND CMAKE_MODULE_PATH
    "${CMAKE_CURRENT_SOURCE_DIR}/cmake"
    "${CMAKE_CURRENT_SOURCE_DIR}/cmake/3rdparty/extra-cmake-modules/find-modules"
    "${CMAKE_CURRENT_SOURCE_DIR}/cmake/3rdparty/kwin"
)

## Find the build internals package.
set(QT_BUILD_INTERNALS_SKIP_CMAKE_MODULE_PATH_ADDITION TRUE)
list(PREPEND CMAKE_PREFIX_PATH
    "${CMAKE_CURRENT_SOURCE_DIR}/cmake"
)
find_package(QtBuildInternals CMAKE_FIND_ROOT_PATH_BOTH)
unset(QT_BUILD_INTERNALS_SKIP_CMAKE_MODULE_PATH_ADDITION)
qt_build_repo_begin()

## QtBase specific configure tests:
include(QtBaseConfigureTests)

## Build System tests:
include(QtBaseCMakeTesting)

## Targets for global features, etc.:
include(QtBaseGlobalTargets)

qt_set_language_standards()

## Should this Qt be static or dynamically linked?
option(BUILD_SHARED_LIBS "Build Qt statically or dynamically" ON)
set(QT_BUILD_SHARED_LIBS ${BUILD_SHARED_LIBS})

## Should this Qt be built with Werror?
option(WARNINGS_ARE_ERRORS "Build Qt with warnings as errors" ${FEATURE_developer_build})

## Should Qt be built using PCH?
option(BUILD_WITH_PCH "Build Qt using precompiled headers?" ON)

## Decide whether tools will be built.
qt_check_if_tools_will_be_built()

## Visit all the directories:
add_subdirectory(src)

if (BUILD_TESTING)
    add_subdirectory(tests)
endif()

if (QT_WILL_BUILD_TOOLS)
    add_subdirectory(qmake)
endif()

# As long as we use the mkspecs (for qplatformdefs.h), we need to always
# install it, especially when cross-compiling.
set(mkspecs_install_dir "${INSTALL_DATADIR}")
qt_path_join(mkspecs_install_dir ${QT_INSTALL_DIR} ${mkspecs_install_dir})

qt_copy_or_install(DIRECTORY "${PROJECT_SOURCE_DIR}/mkspecs"
                   DESTINATION ${mkspecs_install_dir})


qt_build_repo_end()

if(BUILD_EXAMPLES)
    add_subdirectory(examples)
endif()

string(TOLOWER ${CMAKE_BUILD_TYPE} BUILD_TYPE)
string(TOLOWER ${CMAKE_SYSTEM_PROCESSOR} ARCH)
string(TOLOWER ${CMAKE_SYSTEM_NAME} OS)
set(ARCHIVE "${PROJECT_NAME}-${ARCH}-${OS}-${BUILD_TYPE}")
set(CPACK_PACKAGE_FILE_NAME ${ARCHIVE})
set(CPACK_GENERATOR "ZIP")
set(CPACK_INCLUDE_TOPLEVEL_DIRECTORY OFF)
set(CPACK_OUTPUT_FILE_PREFIX ${CMAKE_INSTALL_PREFIX})

include(CPack)


# Generated from skipcleanup.pro.

#####################################################################
## skipcleanup Binary:
#####################################################################

add_qt_executable(skipcleanup
    NO_INSTALL # special case
    OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR} # special case
    GUI
    SOURCES
        tst_skipcleanup.cpp
    PUBLIC_LIBRARIES
        Qt::Test
)

#### Keys ignored in scope 1:.:.:skipcleanup.pro:<TRUE>:
# CONFIG = "-debug_and_release_target"

## Scopes:
#####################################################################

#### Keys ignored in scope 2:.:.:skipcleanup.pro:APPLE_OSX:
# CONFIG = "-app_bundle"

# Generated from test.pro.

#####################################################################
## tst_qclipboard Test:
#####################################################################

add_qt_test(tst_qclipboard
    SOURCES
        ../tst_qclipboard.cpp
    PUBLIC_LIBRARIES
        Qt::Gui
)

## Scopes:
#####################################################################

extend_target(tst_qclipboard CONDITION APPLE_OSX
    PUBLIC_LIBRARIES
        ${FWAppKit}
)

#### Keys ignored in scope 6:.:.:test.pro:NOT ANDROID AND NOT WINRT:
# TEST_HELPER_INSTALLS = "../copier/copier" "../paster/paster"

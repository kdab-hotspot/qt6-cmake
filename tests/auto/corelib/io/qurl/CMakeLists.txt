# Generated from qurl.pro.

#####################################################################
## tst_qurl Test:
#####################################################################

add_qt_test(tst_qurl
    GUI
    SOURCES
        tst_qurl.cpp
    PUBLIC_LIBRARIES
        Qt::Concurrent
)

## Scopes:
#####################################################################

extend_target(tst_qurl CONDITION APPLE
    SOURCES
        tst_qurl_mac.mm
)

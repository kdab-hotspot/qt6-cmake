# Generated from qhostinfo.pro.

#####################################################################
## tst_qhostinfo Test:
#####################################################################

add_qt_test(tst_qhostinfo
    GUI
    SOURCES
        tst_qhostinfo.cpp
    LIBRARIES
        Qt::CorePrivate
        Qt::NetworkPrivate
    PUBLIC_LIBRARIES
        Qt::Network
)

#### Keys ignored in scope 1:.:.:qhostinfo.pro:<TRUE>:
# CONFIG = "testcase"

## Scopes:
#####################################################################

extend_target(tst_qhostinfo CONDITION WIN32
    PUBLIC_LIBRARIES
        ws2_32
)

#### Keys ignored in scope 3:.:.:qhostinfo.pro:WINRT:
# WINRT_MANIFEST.capabilities = "internetClientServer"

# Generated from qhttpsocketengine.pro.

#####################################################################
## tst_qhttpsocketengine Test:
#####################################################################

add_qt_test(tst_qhttpsocketengine
    GUI
    SOURCES
        tst_qhttpsocketengine.cpp
    INCLUDE_DIRECTORIES
        ${QT_SOURCE_TREE}/src/network
    LIBRARIES
        Qt::CorePrivate
        Qt::NetworkPrivate
    PUBLIC_LIBRARIES
        Qt::Network
)

#### Keys ignored in scope 1:.:.:qhttpsocketengine.pro:<TRUE>:
# CONFIG = "testcase"
# MOC_DIR = "tmp"

## Scopes:
#####################################################################

#### Keys ignored in scope 2:.:.:qhttpsocketengine.pro:LINUX:
# CONFIG = "unsupported/testserver"
# QT_TEST_SERVER_LIST = "squid" "danted" "cyrus" "apache2"

extend_target(tst_qhttpsocketengine CONDITION WIN32
    PUBLIC_LIBRARIES
        ws2_32
)

extend_target(tst_qhttpsocketengine CONDITION QT_FEATURE_reduce_exports AND UNIX
    SOURCES
        ${QT_SOURCE_TREE}/src/network/socket/qabstractsocketengine.cpp
        ${QT_SOURCE_TREE}/src/network/socket/qnativesocketengine.cpp
        ${QT_SOURCE_TREE}/src/network/socket/qnativesocketengine_unix.cpp
)

# Generated from qsocks5socketengine.pro.

#####################################################################
## tst_qsocks5socketengine Test:
#####################################################################

add_qt_test(tst_qsocks5socketengine
    GUI
    SOURCES
        tst_qsocks5socketengine.cpp
    INCLUDE_DIRECTORIES
        ${QT_SOURCE_TREE}/src/network
    LIBRARIES
        Qt::CorePrivate
        Qt::NetworkPrivate
    PUBLIC_LIBRARIES
        Qt::Network
)

#### Keys ignored in scope 1:.:.:qsocks5socketengine.pro:<TRUE>:
# CONFIG = "testcase"
# MOC_DIR = "tmp"

## Scopes:
#####################################################################

#### Keys ignored in scope 2:.:.:qsocks5socketengine.pro:LINUX:
# CONFIG = "unsupported/testserver"
# QT_TEST_SERVER_LIST = "danted" "apache2" "cyrus"

extend_target(tst_qsocks5socketengine CONDITION WIN32
    PUBLIC_LIBRARIES
        ws2_32
)

extend_target(tst_qsocks5socketengine CONDITION QT_FEATURE_reduce_exports AND UNIX
    SOURCES
        ${QT_SOURCE_TREE}/src/network/socket/qabstractsocketengine.cpp
        ${QT_SOURCE_TREE}/src/network/socket/qnativesocketengine.cpp
        ${QT_SOURCE_TREE}/src/network/socket/qnativesocketengine_unix.cpp
)

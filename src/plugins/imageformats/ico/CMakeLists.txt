# Generated from ico.pro.

#####################################################################
## qico Plugin:
#####################################################################

add_qt_plugin(qico
    TYPE imageformats
    CLASS_NAME QICOPlugin
    SOURCES
        main.cpp main.h
        qicohandler.cpp qicohandler.h
    LIBRARIES
        Qt::CorePrivate
    PUBLIC_LIBRARIES
        Qt::Core
        Qt::Gui
)

#### Keys ignored in scope 1:.:.:ico.pro:<TRUE>:
# OTHER_FILES = "ico.json"
# _LOADED = "qt_plugin"

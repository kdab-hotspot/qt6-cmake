# Generated from moc.pro.

#####################################################################
## moc Tool:
#####################################################################

add_qt_tool(moc
    BOOTSTRAP
    TOOLS_TARGET Core # special case
    SOURCES
        cbordevice.h
        collectjson.cpp collectjson.h
        generator.cpp generator.h
        main.cpp  # special case
        moc.cpp moc.h
        outputrevision.h
        parser.cpp parser.h
        preprocessor.cpp preprocessor.h
        symbols.h
        token.cpp token.h
        utils.h
    DEFINES
        QT_MOC
        QT_NO_CAST_FROM_ASCII
        QT_NO_CAST_FROM_BYTEARRAY
        QT_NO_COMPRESS
        QT_NO_FOREACH
    INCLUDE_DIRECTORIES
        ${CMAKE_CURRENT_SOURCE_DIR}
        ../../3rdparty/tinycbor/src
)

#### Keys ignored in scope 1:.:.:moc.pro:<TRUE>:
# QMAKE_TARGET_DESCRIPTION = "Qt Meta Object Compiler"
# _LOADED = "qt_tool"
# _OPTION = "host_build"

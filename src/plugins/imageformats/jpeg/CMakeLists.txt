# Generated from jpeg.pro.

qt_find_package(JPEG) # special case

#####################################################################
## qjpeg Plugin:
#####################################################################

add_qt_plugin(qjpeg
    TYPE imageformats
    CLASS_NAME QJpegPlugin
    SOURCES
        main.cpp main.h
        qjpeghandler.cpp qjpeghandler_p.h
    LIBRARIES
        Qt::CorePrivate
        Qt::GuiPrivate
    PUBLIC_LIBRARIES
        JPEG::JPEG
        Qt::Core
        Qt::Gui
)

#### Keys ignored in scope 1:.:.:jpeg.pro:<TRUE>:
# OTHER_FILES = "jpeg.json"
# _LOADED = "qt_plugin"

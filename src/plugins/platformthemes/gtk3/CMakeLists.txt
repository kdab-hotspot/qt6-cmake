# Generated from gtk3.pro.

qt_find_package(GTK3) # special case
qt_find_package(X11) # special case

#####################################################################
## qgtk3 Plugin:
#####################################################################

add_qt_plugin(qgtk3
    TYPE platformthemes
    CLASS_NAME QGtk3ThemePlugin
    SOURCES
        main.cpp
        qgtk3dialoghelpers.cpp qgtk3dialoghelpers.h
        qgtk3menu.cpp qgtk3menu.h
        qgtk3theme.cpp qgtk3theme.h
    DEFINES
        GDK_VERSION_MIN_REQUIRED=GDK_VERSION_3_6
    LIBRARIES
        Qt::CorePrivate
        Qt::GuiPrivate
        Qt::ThemeSupportPrivate
        X11::X11 # special case
    PUBLIC_LIBRARIES
        PkgConfig::GTK3
        Qt::Core
        Qt::Gui
        Qt::ThemeSupport
)

#### Keys ignored in scope 1:.:.:gtk3.pro:<TRUE>:
# PLUGIN_EXTENDS = "-"
# _LOADED = "qt_plugin"

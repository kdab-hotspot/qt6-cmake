# Generated from minimalegl.pro.

#####################################################################
## qminimalegl Plugin:
#####################################################################

add_qt_plugin(qminimalegl
    TYPE platforms
    CLASS_NAME QMinimalEglIntegrationPlugin
    DEFAULT_IF ${QT_QPA_DEFAULT_PLATFORM} MATCHES minimalegl # special case
    SOURCES
        main.cpp
        qminimaleglintegration.cpp qminimaleglintegration.h
        qminimaleglscreen.cpp qminimaleglscreen.h
        qminimaleglwindow.cpp qminimaleglwindow.h
    DEFINES
        QT_EGL_NO_X11
    LIBRARIES
        Qt::CorePrivate
        Qt::EglSupportPrivate
        Qt::EventDispatcherSupportPrivate
        Qt::FontDatabaseSupportPrivate
        Qt::GuiPrivate
    PUBLIC_LIBRARIES
        Qt::Core
        Qt::EglSupport
        Qt::EventDispatcherSupport
        Qt::FontDatabaseSupport
        Qt::Gui
)

#### Keys ignored in scope 1:.:.:minimalegl.pro:<TRUE>:
# OTHER_FILES = "minimalegl.json"
# _LOADED = "qt_plugin"

## Scopes:
#####################################################################

extend_target(qminimalegl CONDITION QT_FEATURE_opengl
    SOURCES
        qminimaleglbackingstore.cpp qminimaleglbackingstore.h
)

#### Keys ignored in scope 3:.:.:minimalegl.pro:NOT TARGET___equals____ss_QT_DEFAULT_QPA_PLUGIN:
# PLUGIN_EXTENDS = "-"

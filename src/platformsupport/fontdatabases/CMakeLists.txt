# Generated from fontdatabases.pro.

qt_find_package(WrapFreetype) # special case
qt_find_package(Fontconfig) # special case

#####################################################################
## FontDatabaseSupport Module:
#####################################################################

add_qt_module(FontDatabaseSupport
    STATIC
    INTERNAL_MODULE
    DEFINES
        QT_NO_CAST_FROM_ASCII
    LIBRARIES
        Qt::CorePrivate
        Qt::GuiPrivate
    PUBLIC_LIBRARIES
        Qt::Core
        Qt::Gui
    PRECOMPILED_HEADER
        "../../corelib/global/qt_pch.h"
)

#### Keys ignored in scope 1:.:.:fontdatabases.pro:<TRUE>:
# MODULE = "fontdatabase_support"
# _LOADED = "qt_module"

## Scopes:
#####################################################################

extend_target(FontDatabaseSupport CONDITION APPLE
    SOURCES
        mac/qcoretextfontdatabase.mm mac/qcoretextfontdatabase_p.h
        mac/qfontengine_coretext.mm mac/qfontengine_coretext_p.h
    LIBRARIES
        ${FWCoreFoundation}
        ${FWCoreGraphics}
        ${FWCoreText}
        ${FWFoundation}
)

extend_target(FontDatabaseSupport CONDITION APPLE_OSX
    LIBRARIES
        ${FWAppKit}
)

extend_target(FontDatabaseSupport CONDITION APPLE AND NOT APPLE_OSX
    LIBRARIES
        ${FWUIKit}
)

extend_target(FontDatabaseSupport CONDITION QT_FEATURE_freetype
    SOURCES
        freetype/qfontengine_ft.cpp freetype/qfontengine_ft_p.h
        freetype/qfreetypefontdatabase.cpp freetype/qfreetypefontdatabase_p.h
    LIBRARIES
        WrapFreetype::WrapFreetype
)

extend_target(FontDatabaseSupport CONDITION UNIX
    SOURCES
        genericunix/qgenericunixfontdatabase_p.h
)

extend_target(FontDatabaseSupport CONDITION QT_FEATURE_fontconfig AND UNIX
    SOURCES
        fontconfig/qfontconfigdatabase.cpp fontconfig/qfontconfigdatabase_p.h
        fontconfig/qfontenginemultifontconfig.cpp fontconfig/qfontenginemultifontconfig_p.h
    LIBRARIES
        Fontconfig::Fontconfig
)

extend_target(FontDatabaseSupport CONDITION WIN32 AND NOT WINRT
    SOURCES
        windows/qwindowsfontdatabase.cpp windows/qwindowsfontdatabase_p.h
        windows/qwindowsfontengine.cpp windows/qwindowsfontengine_p.h
        windows/qwindowsnativeimage.cpp windows/qwindowsnativeimage_p.h
    LIBRARIES
        Qt::GuiPrivate
        advapi32
        gdi32
        ole32
        user32
    PUBLIC_LIBRARIES
        Qt::Gui
)

extend_target(FontDatabaseSupport CONDITION QT_FEATURE_freetype AND WIN32 AND NOT WINRT
    SOURCES
        windows/qwindowsfontdatabase_ft.cpp windows/qwindowsfontdatabase_ft_p.h
)

extend_target(FontDatabaseSupport CONDITION QT_FEATURE_direct2d AND QT_FEATURE_directwrite AND WIN32 AND NOT WINRT
    SOURCES
        windows/qwindowsfontenginedirectwrite.cpp windows/qwindowsfontenginedirectwrite_p.h
    LIBRARIES
        d2d1
)

extend_target(FontDatabaseSupport CONDITION QT_FEATURE_direct2d AND QT_FEATURE_directwrite AND QT_FEATURE_directwrite2 AND WIN32 AND NOT WINRT
    DEFINES
        QT_USE_DIRECTWRITE2
    LIBRARIES
        dwrite_2
)

extend_target(FontDatabaseSupport CONDITION QT_FEATURE_direct2d AND QT_FEATURE_directwrite AND WIN32 AND NOT QT_FEATURE_directwrite2 AND NOT WINRT
    LIBRARIES
        dwrite
)

extend_target(FontDatabaseSupport CONDITION WIN32 AND NOT WINRT AND (NOT QT_FEATURE_direct2d OR NOT QT_FEATURE_directwrite)
    DEFINES
        QT_NO_DIRECTWRITE
)

extend_target(FontDatabaseSupport CONDITION WIN32 AND mingw AND NOT WINRT
    LIBRARIES
        uuid
)

extend_target(FontDatabaseSupport CONDITION WINRT
    SOURCES
        winrt/qwinrtfontdatabase.cpp winrt/qwinrtfontdatabase_p.h
    DEFINES
        __WRL_NO_DEFAULT_LIB__
    LIBRARIES
        Qt::GuiPrivate
        dwrite_1
        ws2_32
    PUBLIC_LIBRARIES
        Qt::Gui
)

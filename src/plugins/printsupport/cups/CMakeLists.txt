# Generated from cups.pro.

qt_find_package(Cups PROVIDED_TARGETS Cups::Cups) # special case

#####################################################################
## cupsprintersupport Plugin:
#####################################################################

add_qt_plugin(cupsprintersupport
    TYPE printsupport
    CLASS_NAME QCupsPrinterSupportPlugin
    SOURCES
        main.cpp
        qcupsprintengine.cpp qcupsprintengine_p.h
        qcupsprintersupport.cpp qcupsprintersupport_p.h
        qppdprintdevice.cpp qppdprintdevice.h
    INCLUDE_DIRECTORIES
        ../../../printsupport/kernel
    LIBRARIES
        Cups::Cups
        Qt::CorePrivate
        Qt::GuiPrivate
        Qt::PrintSupportPrivate
    PUBLIC_LIBRARIES
        Qt::Core
        Qt::Gui
        Qt::PrintSupport
)

#### Keys ignored in scope 1:.:.:cups.pro:<TRUE>:
# MODULE = "cupsprintersupport"
# OTHER_FILES = "cups.json"
# _LOADED = "qt_plugin"

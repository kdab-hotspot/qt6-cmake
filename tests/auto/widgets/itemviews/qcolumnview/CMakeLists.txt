add_qt_test("tst_qcolumnview"
    SOURCES
        ../../../../shared/fakedirmodel.h
        tst_qcolumnview.cpp
    LIBRARIES
        Qt::Widgets
        Qt::WidgetsPrivate
        Qt::GuiPrivate
        Qt::CorePrivate
        Qt::TestPrivate
)

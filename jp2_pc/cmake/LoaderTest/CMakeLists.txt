project(LoaderTest)

list(APPEND LoaderTest_Src
    ${CMAKE_SOURCE_DIR}/Source/Test/Novel/LoaderTest/FileIOTest.cpp
)

add_common_options()

add_executable(${PROJECT_NAME} ${LoaderTest_Src})

set_target_properties(${PROJECT_NAME} PROPERTIES FOLDER Tests/Novel)

include_directories(
    ${CMAKE_SOURCE_DIR}/Source
    ${CMAKE_SOURCE_DIR}/Source/gblinc
    ${CMAKE_SOURCE_DIR}/gtest/googletest/include
)

target_link_libraries( ${PROJECT_NAME}
    AI
    Audio
    EntityDBase
    File
    Game
    GeomDBase
    Loader
    Math
    Physics
    Render3D
    ScreenRenderDWI
    Std
    System
    View

    lz32
    winmm

    dxguid
    dsound
    ddraw

    GTestLibGlobals

    gtest
    gtest_main
)

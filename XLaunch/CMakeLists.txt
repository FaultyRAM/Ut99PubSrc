set(XLAUNCH_PATH ${CMAKE_CURRENT_SOURCE_DIR})
set(XLAUNCH_SRC_PATH ${XLAUNCH_PATH}/Src)
set(XLAUNCH_FILES_SRC
    ${XLAUNCH_SRC_PATH}/XLaunchPrivate.h
    ${XLAUNCH_SRC_PATH}/XLaunch.cpp)
add_executable(XLaunch ${XLAUNCH_FILES_SRC})
source_group(Src ${XLAUNCH_FILES_SRC})
target_compile_definitions(XLaunch PRIVATE GPackage=GPackageXLaunch)
target_include_directories(XLaunch PRIVATE ${X11_INCLUDE_DIR})
target_link_libraries(XLaunch Core Engine ${X11_LIBRARIES})

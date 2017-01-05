set(XDRV_PATH ${CMAKE_CURRENT_SOURCE_DIR})
set(XDRV_INC_PATH ${XDRV_PATH}/Inc)
set(XDRV_SRC_PATH ${XDRV_PATH}/Src)
set(XDRV_FILES_INC
    ${XDRV_INC_PATH}/XDrv.h
    ${XDRV_INC_PATH}/XDrvNative.h)
set(XDRV_FILES_SRC
    ${XDRV_SRC_PATH}/XClient.cpp
    ${XDRV_SRC_PATH}/XDrv.cpp
    ${XDRV_SRC_PATH}/XViewport.cpp)
add_library(XDrv MODULE ${XDRV_FILES_INC} ${XDRV_FILES_SRC})
source_group(Inc ${XDRV_FILES_INC})
source_group(Src ${XDRV_FILES_SRC})
target_compile_definitions(XDrv PRIVATE GPackage=GPackageXDrv)
target_include_directories(XDrv PRIVATE ${XDRV_INC_PATH} ${X11_INCLUDE_DIR})
target_link_libraries(XDrv Core Engine ${X11_LIBRARIES})

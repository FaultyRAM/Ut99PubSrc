set(D3DDRV_PATH ${CMAKE_CURRENT_SOURCE_DIR})
set(D3DDRV_SRC_PATH ${D3DDRV_PATH}/Src)
set(D3DDRV_FILES_SRC
    ${D3DDRV_SRC_PATH}/D3DDrv.h
    ${D3DDRV_SRC_PATH}/D3DDrv.cpp
    ${D3DDRV_SRC_PATH}/Direct3D7.cpp)
add_library(D3DDrv MODULE ${D3DDRV_FILES_SRC})
source_group(Src FILES ${D3DDRV_FILES_SRC})
target_compile_definitions(D3DDrv PRIVATE D3DDRV_EXPORTS ThisPackage=D3DDrv)
target_link_libraries(D3DDrv Core Engine)
if(MSVC)
    target_include_directories(D3DDrv PRIVATE ${DXSDK_INCLUDE})
    target_link_libraries(D3DDrv
        ${DXSDK_LIB}/${CMAKE_STATIC_LIBRARY_PREFIX}dxguid${CMAKE_STATIC_LIBRARY_SUFFIX}
        ${DXSDK_LIB}/${CMAKE_STATIC_LIBRARY_PREFIX}d3dim${CMAKE_STATIC_LIBRARY_SUFFIX})
else(MSVC)
    target_link_libraries(D3DDrv dxguid d3dim)
endif(MSVC)

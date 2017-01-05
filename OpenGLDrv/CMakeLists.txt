set(OPENGLDRV_PATH ${CMAKE_CURRENT_SOURCE_DIR})
set(OPENGLDRV_SRC_PATH ${OPENGLDRV_PATH}/Src)
set(OPENGLDRV_FILES_SRC
    ${OPENGLDRV_SRC_PATH}/OpenGLDrv.h
    ${OPENGLDRV_SRC_PATH}/OpenGLFuncs.h
    ${OPENGLDRV_SRC_PATH}/OpenGL.cpp
    ${OPENGLDRV_SRC_PATH}/OpenGLDrv.cpp)
add_library(OpenGLDrv MODULE ${OPENGLDRV_FILES_SRC})
source_group(Src FILES ${OPENGLDRV_FILES_SRC})
target_compile_definitions(OpenGLDrv PRIVATE OpenGLDRV_EXPORTS ThisPackage=OpenGLDrv)
target_link_libraries(OpenGLDrv Core Engine)

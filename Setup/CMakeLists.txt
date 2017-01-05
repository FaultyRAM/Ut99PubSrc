set(SETUP_PATH ${CMAKE_CURRENT_SOURCE_DIR})
set(SETUP_INC_PATH ${SETUP_PATH}/Inc)
set(SETUP_SRC_PATH ${SETUP_PATH}/Src)
set(SETUP_FILES_INC
    ${SETUP_INC_PATH}/Setup.h
    ${SETUP_INC_PATH}/USetupDefinitionWindows.h)
set(SETUP_FILES_SRC
    ${SETUP_SRC_PATH}/SetupPrivate.h
    ${SETUP_SRC_PATH}/Setup.cpp
    ${SETUP_SRC_PATH}/USetupDefinition.cpp
    ${SETUP_SRC_PATH}/USetupDefinitionWindows.cpp)
set(SETUP_FILES_SRC_RES
    ${SETUP_SRC_PATH}/Res/resource.h
    ${SETUP_SRC_PATH}/Res/idicon_s.ico
    ${SETUP_SRC_PATH}/Res/idicon_t.ico
    ${SETUP_SRC_PATH}/Res/Unreal.ico
    ${SETUP_SRC_PATH}/Res/SetupRes.rc)
set(SETUP_FILES_SETUPPUBSRC
    ${SYSTEM_DIR}/SetupPubSrc.ini
    ${SYSTEM_DIR}/SetupPubSrc.int)
set(SETUP_FILES_SETUPUNREAL
    ${SYSTEM_DIR}/SetupUnreal.ini
    ${SYSTEM_DIR}/SetupUnreal.det
    ${SYSTEM_DIR}/SetupUnreal.est
    ${SYSTEM_DIR}/SetupUnreal.frt
    ${SYSTEM_DIR}/SetupUnreal.int
    ${SYSTEM_DIR}/SetupUnreal.itt)
set(SETUP_FILES_SETUPUNREALPATCH
    ${SYSTEM_DIR}/SetupUnrealPatch.ini
    ${SYSTEM_DIR}/SetupUnrealPatch.int)
set(SETUP_FILES_SETUPFUSION
    ${SYSTEM_DIR}/SetupFusion.ini
    ${SYSTEM_DIR}/SetupFusion.int)
add_executable(Setup WIN32 MACOSX_BUNDLE
    ${SETUP_FILES_INC}
    ${SETUP_FILES_SRC}
    ${SETUP_FILES_SRC_RES}
    ${SETUP_FILES_SETUPPUBSRC}
    ${SETUP_FILES_SETUPUNREAL}
    ${SETUP_FILES_SETUPUNREALPATCH}
    ${SETUP_FILES_SETUPFUSION})
source_group(Inc FILES ${SETUP_FILES_INC})
source_group(Src FILES ${SETUP_FILES_SRC})
source_group(Src\\Res FILES ${SETUP_FILES_SRC_RES})
source_group(SetupPubSrc FILES ${SETUP_FILES_SETUPPUBSRC})
source_group(SetupUnreal FILES ${SETUP_FILES_SETUPUNREAL})
source_group(SetupUnrealPatch FILES ${SETUP_FILES_SETUPUNREALPATCH})
source_group(SetupFusion FILES ${SETUP_FILES_SETUPFUSION})
target_compile_definitions(Setup PRIVATE ThisPackage=Setup)
target_include_directories(Setup PRIVATE ${SETUP_INC_PATH})
target_link_libraries(Setup Core Window)
if(MSVC)
    target_include_directories(Setup PRIVATE ${DXSDK_INCLUDE})
endif(MSVC)

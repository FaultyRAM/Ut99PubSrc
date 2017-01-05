set(CORE_PATH ${CMAKE_CURRENT_SOURCE_DIR})
set(CORE_INC_PATH ${CORE_PATH}/Inc)
set(CORE_LIB_PATH ${CORE_PATH}/Lib)
set(CORE_FILES_INC
    ${CORE_INC_PATH}/Core.h
    ${CORE_INC_PATH}/FCodec.h
    ${CORE_INC_PATH}/FConfigCacheIni.h
    ${CORE_INC_PATH}/FFeedbackContextAnsi.h
    ${CORE_INC_PATH}/FFeedbackContextWindows.h
    ${CORE_INC_PATH}/FFileManagerAnsi.h
    ${CORE_INC_PATH}/FFileManagerArc.h
    ${CORE_INC_PATH}/FFileManagerGeneric.h
    ${CORE_INC_PATH}/FFileManagerLinux.h
    ${CORE_INC_PATH}/FFileManagerPSX2.h
    ${CORE_INC_PATH}/FFileManagerPSX2CD.h
    ${CORE_INC_PATH}/FFileManagerWindows.h
    ${CORE_INC_PATH}/FMallocAnsi.h
    ${CORE_INC_PATH}/FMallocDebug.h
    ${CORE_INC_PATH}/FMallocWindows.h
    ${CORE_INC_PATH}/FOutputDeviceAnsiError.h
    ${CORE_INC_PATH}/FOutputDeviceFile.h
    ${CORE_INC_PATH}/FOutputDeviceNull.h
    ${CORE_INC_PATH}/FOutputDeviceStdout.h
    ${CORE_INC_PATH}/FOutputDeviceWindowsError.h
    ${CORE_INC_PATH}/FRiffChunk.h
    ${CORE_INC_PATH}/UExporter.h
    ${CORE_INC_PATH}/UFactory.h
    ${CORE_INC_PATH}/UnArc.h
    ${CORE_INC_PATH}/UnBits.h
    ${CORE_INC_PATH}/UnBuild.h
    ${CORE_INC_PATH}/UnCache.h
    ${CORE_INC_PATH}/UnCId.h
    ${CORE_INC_PATH}/UnClass.h
    ${CORE_INC_PATH}/UnCoreNative.h
    ${CORE_INC_PATH}/UnCoreNet.h
    ${CORE_INC_PATH}/UnCorObj.h
    ${CORE_INC_PATH}/UnFile.h
    ${CORE_INC_PATH}/UnGnuG.h
    ${CORE_INC_PATH}/UnLinker.h
    ${CORE_INC_PATH}/UnMath.h
    ${CORE_INC_PATH}/UnMem.h
    ${CORE_INC_PATH}/UnMsg.h
    ${CORE_INC_PATH}/UnName.h
    ${CORE_INC_PATH}/UnNames.h
    ${CORE_INC_PATH}/UnObjBas.h
    ${CORE_INC_PATH}/UnObjVer.h
    ${CORE_INC_PATH}/UnScript.h
    ${CORE_INC_PATH}/UnStack.h
    ${CORE_INC_PATH}/UnTemplate.h
    ${CORE_INC_PATH}/UnType.h
    ${CORE_INC_PATH}/UnUnix.h
    ${CORE_INC_PATH}/UnVcWin32.h
    ${CORE_INC_PATH}/UnVcWn32SSE.h)
add_library(Core INTERFACE)
source_group(Inc FILES ${CORE_FILES_INC})
target_include_directories(Core INTERFACE ${CORE_INC_PATH})
if(WIN32)
    target_link_libraries(Core INTERFACE ${CORE_LIB_PATH}/Core.lib)
else(WIN32)
    target_link_libraries(Core INTERFACE -lCore)
endif(WIN32)

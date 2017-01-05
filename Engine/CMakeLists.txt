set(ENGINE_PATH ${CMAKE_CURRENT_SOURCE_DIR})
set(ENGINE_INC_PATH ${ENGINE_PATH}/Inc)
set(ENGINE_LIB_PATH ${ENGINE_PATH}/Lib)
set(ENGINE_FILES_INC
    ${ENGINE_INC_PATH}/AActor.h
    ${ENGINE_INC_PATH}/AAmmo.h
    ${ENGINE_INC_PATH}/ABrush.h
    ${ENGINE_INC_PATH}/ACamera.h
    ${ENGINE_INC_PATH}/ACarcass.h
    ${ENGINE_INC_PATH}/AGameReplicationInfo.h
    ${ENGINE_INC_PATH}/AInventory.h
    ${ENGINE_INC_PATH}/ALevelInfo.h
    ${ENGINE_INC_PATH}/AMover.h
    ${ENGINE_INC_PATH}/APawn.h
    ${ENGINE_INC_PATH}/APickup.h
    ${ENGINE_INC_PATH}/APlayerPawn.h
    ${ENGINE_INC_PATH}/APlayerReplicationInfo.h
    ${ENGINE_INC_PATH}/AWeapon.h
    ${ENGINE_INC_PATH}/AZoneInfo.h
    ${ENGINE_INC_PATH}/Engine.h
    ${ENGINE_INC_PATH}/EngineClasses.h
    ${ENGINE_INC_PATH}/Palette.h
    ${ENGINE_INC_PATH}/S3tc.h
    ${ENGINE_INC_PATH}/ULevelSummary.h
    ${ENGINE_INC_PATH}/UnActor.h
    ${ENGINE_INC_PATH}/UnAnim.h
    ${ENGINE_INC_PATH}/UnAudio.h
    ${ENGINE_INC_PATH}/UnBunch.h
    ${ENGINE_INC_PATH}/UnCamera.h
    ${ENGINE_INC_PATH}/UnChan.h
    ${ENGINE_INC_PATH}/UnCon.h
    ${ENGINE_INC_PATH}/UnConn.h
    ${ENGINE_INC_PATH}/UnDDraw.h
    ${ENGINE_INC_PATH}/UnDemoPenLev.h
    ${ENGINE_INC_PATH}/UnDemoRec.h
    ${ENGINE_INC_PATH}/UnDownload.h
    ${ENGINE_INC_PATH}/UnDynBsp.h
    ${ENGINE_INC_PATH}/UnEngine.h
    ${ENGINE_INC_PATH}/UnEngineGnuG.h
    ${ENGINE_INC_PATH}/UnEngineWin.h
    ${ENGINE_INC_PATH}/UnGame.h
    ${ENGINE_INC_PATH}/UnIn.h
    ${ENGINE_INC_PATH}/UnLevel.h
    ${ENGINE_INC_PATH}/UnMesh.h
    ${ENGINE_INC_PATH}/UnModel.h
    ${ENGINE_INC_PATH}/UnNet.h
    ${ENGINE_INC_PATH}/UnNetDrv.h
    ${ENGINE_INC_PATH}/UnObj.h
    ${ENGINE_INC_PATH}/UnPenLev.h
    ${ENGINE_INC_PATH}/UnPlayer.h
    ${ENGINE_INC_PATH}/UnPrim.h
    ${ENGINE_INC_PATH}/UnReach.h
    ${ENGINE_INC_PATH}/UnRender.h
    ${ENGINE_INC_PATH}/UnRenderIterator.h
    ${ENGINE_INC_PATH}/UnRenderIteratorSupport.h
    ${ENGINE_INC_PATH}/UnRenDev.h
    ${ENGINE_INC_PATH}/UnScrTex.h
    ${ENGINE_INC_PATH}/UnSkeletalMesh.h
    ${ENGINE_INC_PATH}/UnTex.h
    ${ENGINE_INC_PATH}/UnURL.h)
add_library(Engine INTERFACE)
source_group(Inc FILES ${ENGINE_FILES_INC})
target_include_directories(Engine INTERFACE ${ENGINE_INC_PATH})
if(WIN32)
    target_link_libraries(Engine INTERFACE ${ENGINE_LIB_PATH}/Engine.lib)
else(WIN32)
    target_link_libraries(Engine INTERFACE -lEngine)
endif(WIN32)

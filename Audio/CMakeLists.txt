set(AUDIO_PATH ${CMAKE_CURRENT_SOURCE_DIR})
set(AUDIO_INC_PATH ${AUDIO_PATH}/Inc)
set(AUDIO_SRC_PATH ${AUDIO_PATH}/Src)
set(AUDIO_FILES_INC
    ${AUDIO_INC_PATH}/Audio.h
    ${AUDIO_INC_PATH}/AudioCore.h
    ${AUDIO_INC_PATH}/AudioLibrary.h
    ${AUDIO_INC_PATH}/AudioMixer.h
    ${AUDIO_INC_PATH}/AudioNative.h
    ${AUDIO_INC_PATH}/AudioSubsystem.h
    ${AUDIO_INC_PATH}/AudioTypes.h
    ${AUDIO_INC_PATH}/FormatWAV.h)
set(AUDIO_FILES_SRC
    ${AUDIO_SRC_PATH}/AudioPrivate.h
    ${AUDIO_SRC_PATH}/Audio.cpp
    ${AUDIO_SRC_PATH}/AudioCoreLinux.cpp
    ${AUDIO_SRC_PATH}/AudioLibrary.cpp
    ${AUDIO_SRC_PATH}/AudioMixer.cpp
    ${AUDIO_SRC_PATH}/AudioSubsystem.cpp
    ${AUDIO_SRC_PATH}/FormatWAV.cpp)
add_library(Audio MODULE ${AUDIO_FILES_INC} ${AUDIO_FILES_SRC})
source_group(Inc ${AUDIO_FILES_INC})
source_group(Src ${AUDIO_FILES_SRC})
target_compile_definitions(Audio PRIVATE GPackage=GPackageAudio)
target_include_directories(Audio PUBLIC ${AUDIO_INC_PATH})
target_link_libraries(Audio Core Engine pthread)

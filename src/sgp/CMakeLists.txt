file(GLOB LOCAL_JA2_HEADERS ${CMAKE_CURRENT_SOURCE_DIR}/*.h)
set(LOCAL_JA2_SOURCES
    ${CMAKE_CURRENT_SOURCE_DIR}/Button_Sound_Control.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Button_System.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Cursor_Control.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/DirFs.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/FileMan.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Font.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/FPS.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/HImage.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/ImpTGA.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Input.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Line.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/LoadSaveData.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/MouseSystem.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Object_Cache.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/PCX.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Random.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/SGP.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/SGPFile.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/SGPStrings.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/STCI.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Shading.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/SoundMan.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Types.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/VObject.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/VObject_Blitters.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/VSurface.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Video.cc
)

if (WITH_UNITTESTS)
    set(LOCAL_JA2_SOURCES
        ${LOCAL_JA2_SOURCES}
        ${CMAKE_CURRENT_SOURCE_DIR}/FileMan_unittest.cc
        ${CMAKE_CURRENT_SOURCE_DIR}/LoadSaveData_unittest.cc
        ${CMAKE_CURRENT_SOURCE_DIR}/Logger_unittest.cc
        ${CMAKE_CURRENT_SOURCE_DIR}/SGPStrings_unittest.cc
        ${CMAKE_CURRENT_SOURCE_DIR}/string_unittest.cc
    )
endif()

set_property(
    SOURCE ${LOCAL_JA2_SOURCES}
    DIRECTORY ${CMAKE_SOURCE_DIR}
    PROPERTY UNITY_GROUP "SGP"
)

# Remove SoundMan from the SGP unity group because it includes miniaudio,
# building this object file takes longer than all of the other files combined.
set_property(
    SOURCE ${CMAKE_CURRENT_SOURCE_DIR}/SoundMan.cc
    DIRECTORY ${CMAKE_SOURCE_DIR}
    PROPERTY UNITY_GROUP
)

set(JA2_SOURCES
    ${JA2_SOURCES}
    ${LOCAL_JA2_HEADERS}
    ${LOCAL_JA2_SOURCES}
    PARENT_SCOPE
)

set(JA2_INCLUDES
    ${JA2_INCLUDES}
    ${CMAKE_CURRENT_SOURCE_DIR}
    PARENT_SCOPE
)

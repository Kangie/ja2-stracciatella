file(GLOB LOCAL_JA2_HEADERS ${CMAKE_CURRENT_SOURCE_DIR}/*.h)

set(JA2_SOURCES
    ${JA2_SOURCES}
    ${LOCAL_JA2_HEADERS}
    ${CMAKE_CURRENT_SOURCE_DIR}/Assignments.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Auto_Resolve.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Campaign_Init.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Creature_Spreading.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Game_Clock.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Game_Event_Hook.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Game_Events.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Game_Init.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Hourly_Update.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/LoadSaveSectorInfo.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/LoadSaveStrategicMapElement.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/LoadSaveUndergroundSectorInfo.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/MapScreen.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Map_Screen_Helicopter.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Map_Screen_Interface.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Map_Screen_Interface_Border.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Map_Screen_Interface_Bottom.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Map_Screen_Interface_Map.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Map_Screen_Interface_Map_Inventory.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Map_Screen_Interface_TownMine_Info.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Meanwhile.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Merc_Contract.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Player_Command.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/PreBattle_Interface.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Queen_Command.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/QuestText.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Quest_Debug_System.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Quests.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Scheduling.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/StrategicMap.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/StrategicMap_Secrets.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic_AI.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic_Event_Handler.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic_Merc_Handler.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic_Mines.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic_Movement.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic_Movement_Costs.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic_Pathing.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic_Status.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic_Town_Loyalty.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Strategic_Turns.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/SAM_Sites.cc
    ${CMAKE_CURRENT_SOURCE_DIR}/Town_Militia.cc
    PARENT_SCOPE
)

set_property(
    SOURCE
        ${CMAKE_CURRENT_SOURCE_DIR}/LoadSaveSectorInfo.cc
        ${CMAKE_CURRENT_SOURCE_DIR}/LoadSaveStrategicMapElement.cc
        ${CMAKE_CURRENT_SOURCE_DIR}/LoadSaveUndergroundSectorInfo.cc
    DIRECTORY ${CMAKE_SOURCE_DIR}
    PROPERTY UNITY_GROUP "LoadSaveDataTypes"
)

set(JA2_INCLUDES
    ${JA2_INCLUDES}
    ${CMAKE_CURRENT_SOURCE_DIR}
    PARENT_SCOPE
)

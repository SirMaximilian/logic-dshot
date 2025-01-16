cmake_minimum_required(VERSION 3.13)

set(CMAKE_PROJECT_NAME DshotAnalyzer)
project(${CMAKE_PROJECT_NAME})

add_definitions( -DLOGIC2 )
set(CMAKE_EXPORT_COMPILE_COMMANDS TRUE)
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)
include(ExternalAnalyzerSDK)

set(SOURCES 
    source/DshotAnalyzer.cpp
    source/DshotAnalyzerResults.cpp
    source/DshotAnalyzerSettings.cpp
    source/DshotSimulationDataGenerator.cpp
    source/DshotAnalyzer.h
    source/DshotAnalyzerResults.h
    source/DshotAnalyzerSettings.h
    source/DshotSimulationDataGenerator.h
)

add_analyzer_plugin(${CMAKE_PROJECT_NAME} SOURCES ${SOURCES})


#include(sdk/AnalyzerSDKConfig.cmake)
# add_executable(${CMAKE_PROJECT_NAME}
#     source/DshotAnalyzer.cpp
#     source/DshotAnalyzerResults.cpp
#     source/DshotAnalyzerSettings.cpp
#     source/DshotSimulationDataGenerator.cpp
# )
# target_link_libraries(${CMAKE_PROJECT_NAME} PRIVATE Saleae::AnalyzerSDK)

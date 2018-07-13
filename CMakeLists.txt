cmake_minimum_required (VERSION 3.11)
project(dmx_512_analyzer)

# custom CMake Modules are located in the cmake directory.
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(ExternalAnalyzerSDK)

set(SOURCES 
src/Dmx512Analyzer.cpp
src/Dmx512Analyzer.h
src/Dmx512AnalyzerResults.cpp
src/Dmx512AnalyzerResults.h
src/Dmx512AnalyzerSettings.cpp
src/Dmx512AnalyzerSettings.h
src/Dmx512SimulationDataGenerator.cpp
src/Dmx512SimulationDataGenerator.h
)

add_analyzer_plugin(dmx_512_analyzer SOURCES ${SOURCES})

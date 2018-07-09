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

add_library(dmx_512_analyzer SHARED ${SOURCES})
target_link_libraries(dmx_512_analyzer PRIVATE Saleae::AnalyzerSDK)

if(MSVC)
    install(TARGETS dmx_512_analyzer RUNTIME DESTINATION "Analyzers")
else()
    install(TARGETS dmx_512_analyzer LIBRARY DESTINATION "Analyzers")
endif()

set_post_build_destination(dmx_512_analyzer)

###########
# SOURCES #
###########

set(LIB_SRCS
        datatypes/GPSCoordinate.cpp
        datatypes/GPSCoordinateFast.cpp
        datatypes/HexTriangle.cpp
        datatypes/HexVertex.cpp
        logic/StandardCalc.cpp
        pathfinding/AStarPathfinder.cpp
        pathfinding/BasicCostCalculator.cpp
        pathfinding/BasicHexMap.cpp
        pathfinding/HaversineCostCalculator.cpp
        pathfinding/HaversineHeuristic.cpp
        pathfinding/NaiveCostCalculator.cpp
        pathfinding/NaiveHeuristic.cpp
        pathfinding/Pathfinder.cpp
        pathfinding/PathfinderResultPrinter.cpp
        pathfinding/WeatherCostCalculator.cpp
        pathfinding/WeatherHexMap.cpp
        planet/HexPlanet.cpp
        grib/UrlBuilder.cpp
        grib/UrlDownloader.cpp
        grib/gribParse.cpp
        )

set(LIB_HDRS
        common/GeneralDefs.h
        common/ProgressBar.h
        datatypes/GPSCoordinate.h
        datatypes/GPSCoordinateFast.h
        datatypes/HexDefs.h
        datatypes/HexTriangle.h
        datatypes/HexVertex.h
        datatypes/MapData.h
        datatypes/WeatherDatum.h
        logic/StandardCalc.h
        pathfinding/AStarPathfinder.h
        pathfinding/AStarVertex.h
        pathfinding/BasicCostCalculator.h
        pathfinding/BasicHexMap.h
        pathfinding/CostCalculator.h
        pathfinding/HaversineCostCalculator.h
        pathfinding/HaversineHeuristic.h
        pathfinding/Heuristic.h
        pathfinding/NaiveCostCalculator.h
        pathfinding/NaiveHeuristic.h
        pathfinding/Pathfinder.h
        pathfinding/PathfinderResultPrinter.h
        pathfinding/WeatherCostCalculator.h
        pathfinding/WeatherHexMap.h
        planet/HexPlanet.h
        grib/UrlBuilder.h
        grib/UrlDownloader.h
        grib/gribParse.h
        )

# Define the src_core library target
add_library(src_core STATIC ${LIB_SRCS} ${LIB_HDRS})

# Link dependencies
add_dependencies(src_core protofiles)

target_link_libraries(src_core ${CORE_LIBS})

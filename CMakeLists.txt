project(projekt)
cmake_minimum_required(VERSION 2.8)

# Find OpenCV
find_package(OpenCV REQUIRED)
if (OpenCV_FOUND)
    message("-- OpenCV ${OpenCV_VERSION} was found")
    include_directories(${OpenCV_INCLUDE_DIRS})
else(OpenCV_FOUND)
    message(FATAL_ERROR "OpenCV was not found")
endif(OpenCV_FOUND)

# Definitions
add_definitions(-DPROJECT_SOURCE_DIR=\"${PROJECT_SOURCE_DIR}\")


# Declare a cpp executable (czerwone)
add_executable(projekt1 src/czerwone.cpp)
# Specify libraries to link a library or executable target against (lab3)
target_link_libraries(projekt1 ${OpenCV_LIBS})

# Declare a cpp executable (zielone)
add_executable(projekt2 src/zielone.cpp)
# Specify libraries to link a library or executable target against (lab3)
target_link_libraries(projekt2 ${OpenCV_LIBS})

# Declare a cpp executable (czerwone_film)
add_executable(projekt3 src/czerwone_video.cpp)
# Specify libraries to link a library or executable target against (lab3)
target_link_libraries(projekt3 ${OpenCV_LIBS})

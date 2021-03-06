project(tcg)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(${PROJECT_NAME}
    src/main.cpp
    src/initialize.cpp
    src/utils.cpp
    src/utils.hpp
    src/command.cpp
    src/command.hpp
    src/names.txt
    src/create.cpp
    src/freeze.cpp
    src/list.cpp
    src/set.cpp
    src/show.cpp
    src/self.cpp
    src/help.cpp
)

find_package(Boost 1.71.0 COMPONENTS filesystem REQUIRED)
add_subdirectory(third_party/spdlog EXCLUDE_FROM_ALL)
add_subdirectory(third_party/fmt EXCLUDE_FROM_ALL)
target_link_libraries(${PROJECT_NAME} ${Boost_FILESYSTEM_LIBRARY} fmt::fmt spdlog::spdlog)

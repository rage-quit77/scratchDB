cmake_minimum_required(VERSION 3.12)

add_executable(scratchDB-cli main.cpp)

target_link_libraries(scratchDB-cli PRIVATE scratchDB)

target_compile_features(scratchDB-cli PRIVATE cxx_std_17)

include_directories(${scratchDB_SOURCE_DIR})

install(TARGETS scratchDB-cli
  RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR} 
)

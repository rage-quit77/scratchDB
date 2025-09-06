cmake_minimum_required(VERSION 3.12)

add_executable(scratchDB-tests
	dbmanagement-tests.cpp
	hashing-tests.cpp
	keyvalue-tests.cpp
	performance-tests.cpp
)

include_directories(${scratchDB_SOURCE_DIR})

# This assume highwayhash is a sub-module of this repo..
include_directories(${scratchDB_SOURCE_DIR}/highwayhash)
# if you have built highwayhash as a peer repo, use this line
#include_directories(${scratchDB_SOURCE_DIR}/../highwayhash)

target_link_libraries(scratchDB-tests PRIVATE scratchDB)

target_compile_features(scratchDB-tests PRIVATE cxx_std_17)

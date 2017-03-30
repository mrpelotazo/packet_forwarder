cmake_minimum_required(VERSION 3.2)

project(lora_pkt_fwd)
include(GNUInstallDirs)

find_package(libloragw REQUIRED)
find_package(Threads REQUIRED)

#-----------------------------------------------------------------------------
# pktfwd version
#-----------------------------------------------------------------------------
set(PKTFWD_VERSION_MAJOR     3)
set(PKTFWD_VERSION_MINOR     1)
set(PKTFWD_VERSION_PATCH     0)
set(PKTFWD_VERSION   "${LIBLORAGW_VERSION_MAJOR}.${LIBLORAGW_VERSION_MINOR}.${LIBLORAGW_VERSION_PATCH}")

#-----------------------------------------------------------------------------
# pktfwd sources
#-----------------------------------------------------------------------------
file(GLOB PKTFWD_SOURCES ${PROJECT_SOURCE_DIR}/src/*)

#-----------------------------------------------------------------------------
# pktfwd target
#-----------------------------------------------------------------------------
add_executable(pktfwd ${PKTFWD_SOURCES})
set_target_properties(pktfwd PROPERTIES OUTPUT_NAME lora_pkt_fwd)

#-----------------------------------------------------------------------------
# pktfwd includes
#-----------------------------------------------------------------------------
target_include_directories(pktfwd PUBLIC
	${PROJECT_SOURCE_DIR}/inc
)

#-----------------------------------------------------------------------------
# pktfwd linking
#-----------------------------------------------------------------------------

target_link_libraries(pktfwd PRIVATE loragw Threads::Threads m)

#-----------------------------------------------------------------------------
# install targets
#-----------------------------------------------------------------------------
install(TARGETS pktfwd DESTINATION ${CMAKE_INSTALL_FULL_BINDIR})

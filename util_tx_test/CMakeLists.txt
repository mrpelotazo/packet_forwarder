cmake_minimum_required(VERSION 3.2)

project(util_tx_test)
include(GNUInstallDirs)

#-----------------------------------------------------------------------------
# pktfwd sources
#-----------------------------------------------------------------------------
file(GLOB UTLTXTST_SOURCES ${PROJECT_SOURCE_DIR}/src/*)

#-----------------------------------------------------------------------------
# pktfwd target
#-----------------------------------------------------------------------------
add_executable(utltxtst ${UTLTXTST_SOURCES})
set_target_properties(utltxtst PROPERTIES OUTPUT_NAME util_tx_test)

#-----------------------------------------------------------------------------
# pktfwd includes
#-----------------------------------------------------------------------------
target_include_directories(utltxtst PRIVATE
	${PROJECT_SOURCE_DIR}/inc
)

#-----------------------------------------------------------------------------
# install targets
#-----------------------------------------------------------------------------
install(TARGETS utltxtst DESTINATION ${CMAKE_INSTALL_FULL_BINDIR})

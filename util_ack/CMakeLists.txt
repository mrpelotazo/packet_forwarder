cmake_minimum_required(VERSION 3.2)

project(util_ack)
include(GNUInstallDirs)

#-----------------------------------------------------------------------------
# utlack sources
#-----------------------------------------------------------------------------
file(GLOB UTLACK_SOURCES ${PROJECT_SOURCE_DIR}/src/*)

#-----------------------------------------------------------------------------
# utlack target
#-----------------------------------------------------------------------------
add_executable(utlack ${UTLACK_SOURCES})
set_target_properties(utlack PROPERTIES OUTPUT_NAME util_ack)

#-----------------------------------------------------------------------------
# utlack includes
#-----------------------------------------------------------------------------
target_include_directories(utlack PRIVATE
	${PROJECT_SOURCE_DIR}/inc
)

#-----------------------------------------------------------------------------
# install targets
#-----------------------------------------------------------------------------
install(TARGETS utlack DESTINATION opt/semtech)

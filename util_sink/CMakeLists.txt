cmake_minimum_required(VERSION 3.2)

project(util_sink)
include(GNUInstallDirs)

#-----------------------------------------------------------------------------
# utlsnk sources
#-----------------------------------------------------------------------------
file(GLOB UTLACK_SOURCES ${PROJECT_SOURCE_DIR}/src/*)

#-----------------------------------------------------------------------------
# utlsnk target
#-----------------------------------------------------------------------------
add_executable(utlsnk ${UTLACK_SOURCES})
set_target_properties(utlsnk PROPERTIES OUTPUT_NAME util_sink)

#-----------------------------------------------------------------------------
# utlsnk includes
#-----------------------------------------------------------------------------
target_include_directories(utlsnk PRIVATE
	${PROJECT_SOURCE_DIR}/inc
)

#-----------------------------------------------------------------------------
# install targets
#-----------------------------------------------------------------------------
install(TARGETS utlsnk DESTINATION opt/semtech)

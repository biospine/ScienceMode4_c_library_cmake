
cmake_minimum_required (VERSION 3.0.0)
set(CMAKE_CONFIGURATION_TYPES "Debug;Release;RelWithDebInfo" CACHE STRING "" FORCE)

set(SMPT_VERSION_MAJOR 4)
set(SMPT_VERSION_MINOR 0)
set(SMPT_VERSION_PATCH 0)

project(ScienceModeProtocol)

if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 20)
endif()

set(smpt_root ScienceMode4_c_library/ScienceMode_Library)

set(SMPT_LIBRARY_NAME sciencemode_protocol)

set(general_HEADER_DIR
    ${smpt_root}/include/general/packet
    ${smpt_root}/include/general/packet_input_buffer
    ${smpt_root}/include/general/packet_output_buffer
    ${smpt_root}/include/general/serial_port
    ${smpt_root}/include/general
)

set(general_HEADERS
    ${smpt_root}/include/general/smpt_client.h
    ${smpt_root}/include/general/smpt_client_data.h
    ${smpt_root}/include/general/smpt_client_cmd_lists.h
    ${smpt_root}/include/general/smpt_definitions.h
    ${smpt_root}/include/general/smpt_definitions_internal.h
    ${smpt_root}/include/general/smpt_definitions_data_types.h
    ${smpt_root}/include/general/smpt_messages.h
    ${smpt_root}/include/general/packet/smpt_packet_general.h
    ${smpt_root}/include/general/packet/smpt_packet_internal.h
    ${smpt_root}/include/general/packet/smpt_packet_validity.h
    ${smpt_root}/include/general/packet/smpt_packet_utils.h
    ${smpt_root}/include/general/packet/smpt_packet_client.h
    ${smpt_root}/include/general/packet/smpt_packet_server.h
    ${smpt_root}/include/general/packet_input_buffer/smpt_packet_input_buffer.h
    ${smpt_root}/include/general/packet_input_buffer/smpt_packet_input_buffer_definitions.h
    ${smpt_root}/include/general/packet_input_buffer/smpt_packet_input_buffer_internal.h
    ${smpt_root}/include/general/packet_output_buffer/smpt_packet_output_buffer.h
    ${smpt_root}/include/general/serial_port/smpt_serial_port.h
    ${smpt_root}/include/general/serial_port/smpt_serial_port_windows.h
    ${smpt_root}/include/general/serial_port/smpt_serial_port_linux.h
    ${smpt_root}/include/general/serial_port/smpt_serial_port_macos.h
    ${smpt_root}/include/general/smpt_definitions_file_transfer.h
    ${smpt_root}/include/general/smpt_file.h
    ${smpt_root}/include/general/smpt_packet_number_generator.h
    ${smpt_root}/include/general/smpt_definitions_power.h
    ${smpt_root}/include/general/smpt_client_power.h
    ${smpt_root}/include/general/smpt_client_utils.h
)

set(general_SOURCES
    ${smpt_root}/src/general/smpt_messages.c
    ${smpt_root}/src/general/smpt_client.c
    ${smpt_root}/src/general/smpt_client_data.c
    ${smpt_root}/src/general/smpt_client_cmd_lists.c
    ${smpt_root}/src/general/smpt_definitions_data_types.c

    ${smpt_root}/src/general/packet/smpt_packet_general.c
    ${smpt_root}/src/general/packet/smpt_packet_internal.c
    ${smpt_root}/src/general/packet/smpt_packet_validity.c
    ${smpt_root}/src/general/packet/smpt_packet_utils.c
    ${smpt_root}/src/general/packet/smpt_packet_client.c
    ${smpt_root}/src/general/packet/smpt_packet_server.c

    ${smpt_root}/src/general/packet_input_buffer/smpt_packet_input_buffer.c
    ${smpt_root}/src/general/packet_input_buffer/smpt_packet_input_buffer_internal.c
    ${smpt_root}/src/general/packet_output_buffer/smpt_packet_output_buffer.c

    ${smpt_root}/src/general/serial_port/smpt_serial_port.c
    ${smpt_root}/src/general/serial_port/smpt_serial_port_windows.c
    ${smpt_root}/src/general/serial_port/smpt_serial_port_linux.c
    ${smpt_root}/src/general/serial_port/smpt_serial_port_macos.c
    ${smpt_root}/src/general/smpt_definitions_file_transfer.c
    ${smpt_root}/src/general/smpt_file.c
    ${smpt_root}/src/general/smpt_packet_number_generator.c
    ${smpt_root}/src/general/smpt_definitions_power.c
    ${smpt_root}/src/general/smpt_client_utils.c
    ${smpt_root}/src/general/smpt_client_power.c
)

set(low_level_HEADER_DIR
    ${smpt_root}/include/low-level
)

set(low_level_HEADERS
    ${smpt_root}/include/low-level/smpt_ll_client.h
    ${smpt_root}/include/low-level/smpt_ll_definitions.h
    ${smpt_root}/include/low-level/smpt_ll_packet_client.h
    ${smpt_root}/include/low-level/smpt_ll_packet_server.h
    ${smpt_root}/include/low-level/smpt_ll_packet_validity.h
    ${smpt_root}/include/low-level/smpt_ll_definitions_data_types.h
    ${smpt_root}/include/low-level/smpt_ll_messages.h
)

set(low_level_SOURCES
    ${smpt_root}/src/low-level/smpt_ll_packet_client.c
    ${smpt_root}/src/low-level/smpt_ll_packet_server.c
    ${smpt_root}/src/low-level/smpt_ll_client.c
    ${smpt_root}/src/low-level/smpt_ll_packet_validity.c
    ${smpt_root}/src/low-level/smpt_ll_messages.c
    ${smpt_root}/src/low-level/smpt_ll_definitions_data_types.c
)

set(mid_level_HEADER_DIR
    ${smpt_root}/include/mid-level
)

set(mid_level_HEADERS
    ${smpt_root}/include/mid-level/smpt_ml_packet_client.h
    ${smpt_root}/include/mid-level/smpt_ml_definitions_data_types.h
    ${smpt_root}/include/mid-level/smpt_ml_packet_server.h
    ${smpt_root}/include/mid-level/smpt_ml_packet_validity.h
    ${smpt_root}/include/mid-level/smpt_ml_client.h
    ${smpt_root}/include/mid-level/smpt_ml_definitions.h
    ${smpt_root}/include/mid-level/smpt_ml_packet_utils.h
)
set(mid_level_SOURCES
    ${smpt_root}/src/mid-level/smpt_ml_packet_client.c
    ${smpt_root}/src/mid-level/smpt_ml_definitions_data_types.c
    ${smpt_root}/src/mid-level/smpt_ml_packet_server.c
    ${smpt_root}/src/mid-level/smpt_ml_packet_validity.c
    ${smpt_root}/src/mid-level/smpt_ml_client.c
    ${smpt_root}/src/mid-level/smpt_ml_packet_utils.c
)

set(dyscom_level_HEADER_DIR
    ${smpt_root}/include/dyscom-level
)
set(dyscom_level_HEADERS
	${smpt_root}/include/dyscom-level/smpt_dl_client.h
	${smpt_root}/include/dyscom-level/smpt_dl_definitions_data_types.h
	${smpt_root}/include/dyscom-level/smpt_dl_definitions.h
	${smpt_root}/include/dyscom-level/smpt_dl_packet_client.h
	${smpt_root}/include/dyscom-level/smpt_dl_packet_server.h
	${smpt_root}/include/dyscom-level/smpt_dl_packet_utils.h
	${smpt_root}/include/dyscom-level/smpt_dl_packet_validity.h
)

set(dyscom_level_SOURCES
    ${smpt_root}/src/dyscom-level/smpt_dl_packet_client.c
    ${smpt_root}/src/dyscom-level/smpt_dl_definitions_data_types.c
    ${smpt_root}/src/dyscom-level/smpt_dl_packet_server.c
    ${smpt_root}/src/dyscom-level/smpt_dl_packet_validity.c
    ${smpt_root}/src/dyscom-level/smpt_dl_client.c
    ${smpt_root}/src/dyscom-level/smpt_dl_packet_utils.c
)


configure_file(${CMAKE_CURRENT_SOURCE_DIR}/versioninfo.rc.cmake.in versioninfo.rc @ONLY)

set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)
set(BUILD_SHARED_LIBS TRUE)
include (GenerateExportHeader)
add_library(
    ${SMPT_LIBRARY_NAME}
    SHARED
    ${general_SOURCES}
    ${low_level_SOURCES}
    ${mid_level_SOURCES}
    ${dyscom_level_SOURCES}
    ${general_HEADERS}
    ${low_level_HEADERS}
    ${mid_level_HEADERS}
    ${dyscom_level_HEADERS}
    "${CMAKE_CURRENT_BINARY_DIR}/versioninfo.rc")

set(all_HEADERS
    ${general_HEADERS} ${low_level_HEADERS} ${mid_level_HEADERS} ${dyscom_level_HEADERS}
)
set_target_properties(${SMPT_LIBRARY_NAME} PROPERTIES
	FRAMEWORK TRUE
	PUBLIC_HEADER "${all_HEADERS}"
)

target_compile_definitions(${SMPT_LIBRARY_NAME} PUBLIC SMPT_DLL SMPT_EXPORTS)
target_link_libraries(${SMPT_LIBRARY_NAME} PUBLIC)
target_include_directories(${SMPT_LIBRARY_NAME}
	PUBLIC  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
	$<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>
    PRIVATE
    ${general_HEADER_DIR}
    ${low_level_HEADER_DIR}
    ${mid_level_HEADER_DIR}
    ${dyscom_level_HEADER_DIR})

install(
	TARGETS ${SMPT_LIBRARY_NAME}
	EXPORT ${SMPT_LIBRARY_NAME}_Exports
	RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR} COMPONENT smpt-library
	ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR} COMPONENT smpt-library
	PUBLIC_HEADER DESTINATION include/smpt/ COMPONENT smpt-library
	INCLUDES DESTINATION include/
)

#add_executable(main main.cpp )
#target_link_libraries(main PUBLIC ${SMPT_LIBRARY_NAME})
#target_include_directories(main PUBLIC)


# Install ScienceModeProtocol and .cmake files
install(EXPORT ${SMPT_LIBRARY_NAME}_Exports
  NAMESPACE ${PROJECT_NAME}::
  FILE ${PROJECT_NAME}Targets.cmake
  DESTINATION lib/cmake/${PROJECT_NAME}
  COMPONENT smpt-library
)

# Create config file
include(CMakePackageConfigHelpers)
write_basic_package_version_file(
  "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}ConfigVersion.cmake"
  VERSION ${SMPT_VERSION_MAJOR}.${SMPT_VERSION_MINOR}.${SMPT_VERSION_PATCH}
  COMPATIBILITY AnyNewerVersion
)

configure_package_config_file(
  "${CMAKE_CURRENT_SOURCE_DIR}/cmake/${PROJECT_NAME}Config.cmake.in"
  "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}Config.cmake"
  INSTALL_DESTINATION lib/cmake/${SMPT_LIBRARY_NAME}
)

# Install the config and version files
install(FILES
  "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}Config.cmake"
  "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}ConfigVersion.cmake"
  DESTINATION lib/cmake/${PROJECT_NAME}
  COMPONENT smpt-library
)
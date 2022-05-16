AUX_SOURCE_DIRECTORY(.  gst_app_source_files)
list(APPEND gst_app_sources ${gst_app_source_files})

add_executable(${CMAKE_PROJECT_NAME} ${gst_app_sources})

target_link_libraries(${CMAKE_PROJECT_NAME} PRIVATE ${GLIB_LIBRARIES} ${GSTLIB} ${GOBJLIB})
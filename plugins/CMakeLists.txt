AUX_SOURCE_DIRECTORY(.  gst_plugin_source_files)
list(APPEND gst_plugin_sources ${gst_plugin_source_files})

message("Files are ${gst_plugin_sources}")
message("Project source dir ${PROJECT_SOURCE_DIR}")

#the library name must be same with the 3rd argument in GST_PLUGIN_DEFINE
add_library(${CMAKE_PROJECT_NAME} SHARED ${gst_plugin_sources})

target_include_directories(${CMAKE_PROJECT_NAME} PRIVATE .)
target_link_libraries(${CMAKE_PROJECT_NAME} PRIVATE ${GST_LIBRARIES} ${GSTBASE_LIBRARIES})
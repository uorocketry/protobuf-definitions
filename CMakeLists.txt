find_package(Protobuf REQUIRED)
protobuf_generate_cpp(PROTO_SRCS PROTO_HDRS ArduinoComm.proto)
add_library(protobufDef ${PROTO_SRCS} ${PROTO_HDRS})
target_include_directories(protobufDef PUBLIC ${CMAKE_CURRENT_BINARY_DIR} ${Protobuf_INCLUDE_DIRS})
target_link_libraries(protobufDef ${Protobuf_LIBRARIES})
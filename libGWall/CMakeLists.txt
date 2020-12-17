set(LIB_SRC hello.c)
add_library(libGWall ${LIB_SRC})
# set(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/lib)
set_target_properties(libGWall PROPERTIES OUTPUT_NAME "GWall") #给生成的.a重命名
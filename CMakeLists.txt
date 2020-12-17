# cmake_minimum_required(VERSION 3.0.0)
# project(GWall VERSION 0.1.0)

# include(CTest)
# enable_testing()

# set(SRC_LIST main.c hello.c)
# add_executable(hello ${SRC_LIST})

# set(CPACK_PROJECT_NAME ${PROJECT_NAME})
# set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
# include(CPack)


#----------------------------------------------------------

# 1、执行单个文件
# project(HELLO)
# set(SRC_LIST main.c)
# add_executable(hello ${SRC_LIST})

# 目录结构
# +
# | 
# +--- main.c
# +--- CMakeList.txt
# |
# /--+ build/
#    |
#    +--- hello.exe

#----------------------------------------------------------

# 2、执行多个文件
# project(GWall)
# set(SRC_LIST main.c hello.c)
# add_executable(hello ${SRC_LIST})

# 目录结构
# +
# | 
# +--- main.c
# +--- hello.h
# +--- hello.c
# +--- CMakeList.txt
# |
# /--+ build/
#    |
#    +--- hello.exe

#----------------------------------------------------------

# 3、将hello.c生成一个库，然后再使用
# project(GWall)
# set(LIB_SRC hello.c)
# set(APP_SRC main.c)
# add_library(libhello ${LIB_SRC})
# add_executable(hello ${APP_SRC})
# target_link_libraries(hello libhello)
# set_target_properties(libhello PROPERTIES OUTPUT_NAME "GWall")

# 目录结构
# +
# | 
# +--- main.c
# +--- hello.h
# +--- hello.c
# +--- CMakeList.txt
# |
# /--+ build/
#    |
#    +--- hello.exe
#    +--- libhello.lib

#----------------------------------------------------------

# 4、可执行文件在 bin 目录，库文件在 lib 目录
# project(GWall)
# add_subdirectory(src)
# add_subdirectory(libhello)

# +
# |
# +--- CMakeList.txt
# +--+ src/
# |  |
# |  +--- main.c
# |  /--- CMakeList.txt
# |
# +--+ libhello/
# |  |
# |  +--- hello.h
# |  +--- hello.c
# |  /--- CMakeList.txt
# |
# /--+ build/

#----------------------------------------------------------

# 5让可执行文件在 bin 目录，库文件在 lib 目录
project(GWall)
add_subdirectory(Project1 bin)
add_subdirectory(Project2 bin)
add_subdirectory(libGWall lib)

# + build/
#    |
#    +--+ bin/
#    |  |
#    |  /--- hello.exe
#    |
#    /--+ lib/
#       |
#       /--- hello.lib
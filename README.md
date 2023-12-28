CMakeList设置的变量set(BUILD_USER "OSWIN")在cpp中使用的两种方式：

1.configure_file (${CMAKE_CURRENT_LIST_DIR}/config.h.in ${CMAKE_CURRENT_BINARY_DIR}/config.h)
  #cmakedefine BUILD_USER "@BUILD_USER@"=>(生成头文件config.h）#define BUILD_USER "OSWIN"
2.add_definitions("-DBUILD_USER=\"${BUILD_USER}\"")

在main.cpp中调用：
printf("BUILD_USER: %s",BUILD_USER);

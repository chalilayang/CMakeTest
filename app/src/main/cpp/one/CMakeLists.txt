#生成so动态库
ADD_LIBRARY(one SHARED ./one.cpp)

target_link_libraries(one log)
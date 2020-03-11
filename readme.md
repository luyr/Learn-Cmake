
# 注释 
- Type:
   1. PUBLIC 表示对lib本身和链接了lib的文件适用
   2. INTERFACE 表示仅对链接了lib的文件适用
   3. PRIVATE 表示仅对lib本身适用

- Target: Target在cmake中指由 add_executable() 或 add_library() 生成的文件

---
# 配置编译相关
*设定cmake版本*  

```cmake
cmake_minimum_required(VERSION <version>)
```

*设定proj名，同时会给 PROJECT_NAME 和 PROJECT VERSION 赋值*
```cmake
project(<proj name> VERSION <version#>)
```

*添加子文件夹*
```cmake
add_subdirectory(<dir name>)
```

*添加库*
```cmake
add_library(
    <lib name> 
    <lib type(STATIC/SHARED)>
    <source file>
    <source file>
)
```

*添加可执行文件*
```cmake
add_executable(
    <exe name>
    <source file>
)
```

*链接 lib 到 指定 target*
```cmake
target_link_libraries(
    <target>
    <type>
    <lib name>
)
```
*设定 target 的路径*
```cmake
target_include_directories(
    <target> 
    <type> # type 的用法参考顶部注释
    <path> # path 为此 CMakeLists 所在的目录
) 
```

*为指定 target 添加预编译指令*
```cmake
target_compile_definitions(
    <lib name> 
    <type> # type 的用法参考顶部注释
    <definition(ID=4)> # 将 ID 赋值为4
)
```
---
# Script 相关

*变量赋值*  
`set(<var name> <value>)`
 
*输出到终端*  
`message(STATUS "<content>")`

*控制流*  
1. 条件语句
```cmake
if()
    # code
elseif()
    # code
else()
    # code
endif()
```
2. while 循环  
```cmake
while()
    # code
endwhile()
```
3. foreach 循环
```cmake
# version 1
foreach(item IN ITEMS foo bar baz qux)
    # code
endforeach

# version 2
foreach(idx RANGE 100) 
# could also be foreach(idx RANGE <起始值><终止值><步长>)
    # code
endforeach

```

*其他*  
`EQUAL` 判断数学上是否相等  
`STREQUAL` 判断字符串是否相等  
`NOT`, `AND`, `OR` 逻辑运算  
`LESS` 小于
`MATCHES` 匹配字符串  
```math(EXPR <var> "${var} + 1")``` 数学运算 var += 1



 



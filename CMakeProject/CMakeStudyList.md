> CMake 是一个跨平台的自动化构建系统，它使用一个名为 CMakeLists.txt 的配置文件来描述如何构建软件。掌握 CMake 对于开发跨平台的应用程序非常重要。以下是一些常用的 CMake 功能模块和命令，它们对于大多数项目来说都是很有帮助的：
>
> 1. **基本构建设置**
>    - `cmake_minimum_required(VERSION <version>)`：指定项目所需的最低 CMake 版本。
>    - `project(<PROJECT-NAME> [VERSION <major>[.<minor>[.<patch>[.<tweak>]]]] [DESCRIPTION <description>] [HOMEPAGE_URL <url>] [LANGUAGES <language-name>...])`：定义项目名称、版本等信息。
>
> 2. **添加源码目录与二进制目录**
>    - `add_subdirectory(source_dir [binary_dir])`：将给定的源代码目录加入到构建过程中。
>
> 3. **添加库和可执行文件**
>    - `add_library(<name> [STATIC | SHARED | MODULE] [EXCLUDE_FROM_ALL] source1 [source2 ...])`：创建一个库目标。
>    - `add_executable(<name> [WIN32] [MACOSX_BUNDLE] [EXCLUDE_FROM_ALL] source1 [source2 ...])`：创建一个可执行文件目标。
>
> 4. **链接库**
>    - `target_link_libraries(<target> [item1 [item2 [...]]])`：为指定的目标添加需要链接的库。
>
> 5. **查找包/库**
>    - `find_package(<PackageName> [version] [EXACT] [QUIET] [MODULE] [REQUIRED] [[COMPONENTS] [components...]] [OPTIONAL_COMPONENTS components...])`：用来查找外部库，并设置相应的变量。
>    - `pkg_check_modules(<prefix> [REQUIRED] <module1> [<module2> ...])`：用于检查 PKG_CONFIG 路径下的模块。
>
> 6. **设置编译选项**
>    - `set(CMAKE_CXX_STANDARD 11)`：设置 C++ 标准。
>    - `target_compile_options(<target> [BEFORE] <INTERFACE|PUBLIC|PRIVATE> [items1...] <INTERFACE|PUBLIC|PRIVATE> [items2...]...)`：为目标添加编译选项。
>
> 7. **条件控制**
>    - `if(<condition>)` / `else()` / `elseif(<condition>)` / `endif()`：基于条件执行部分 CMake 代码。
>    - `option(<option_variable> "help string describing the option" [initial value])`：向用户呈现一个开关选项。
>
> 8. **安装规则**
>    - `install(TARGETS targets... [EXPORT <export-name>] [ARCHIVE DESTINATION dir] [LIBRARY DESTINATION dir] [RUNTIME DESTINATION dir] [FRAMEWORK DESTINATION dir] [BUNDLE DESTINATION dir] [INCLUDES DESTINATION dir] [PUBLIC_HEADER DESTINATION dir] [PRIVATE_HEADER DESTINATION dir] [RESOURCE DESTINATION dir] [NAMELINK_COMPONENT component_name] [OPTIONAL_COMPONENTS components...] [PERMISSIONS permissions...] [CONFIGURATIONS [Debug|Release|...]] [COMPONENT component] [EXCLUDE_FROM_ALL])`：定义安装路径等。
>
> 9. **生成器表达式**
>    - `$<IF:condition,then,else>` 和其他生成器表达式：在配置阶段根据某些条件动态地改变属性或行为。
>
> 10. **测试**
>     - `enable_testing()`：启用测试功能。
>     - `add_test(NAME <name> COMMAND <command> [arg1 arg2 ...])`：添加一个测试案例。
>
> 11. **自定义命令和目标**
>     - `add_custom_command(TARGET target PRE_BUILD | PRE_LINK | POST_BUILD COMMAND command1 [ARGS] [args1...] [COMMAND command2 [ARGS] [args2...] ...] [MAIN_DEPENDENCY depend] [DEPENDS [depends...]] [IMPLICIT_DEPENDS <lang1> depend1 ...] [WORKING_DIRECTORY dir] [COMMENT comment] [VERBATIM] [APPEND])`：为特定目标添加自定义构建步骤。
>     - `add_custom_target(Name [ALL] [command1 [args1...]] [COMMAND command2 [args2...] ...] [DEPENDS depend depend depend ... ] [WORKING_DIRECTORY dir] [COMMENT comment] [JOB_POOL job_pool] [VERBATIM] [SOURCES src1 [src2 ...]])`：创建一个没有输出的伪目标。
>
> 12. **导出和导入配置**
>     - `export(TARGETS targets... FILE filename)`: 将目标导出到一个文件中。
>     - `import(EXPORT project-targets FILE filename)`: 从文件中导入目标。
>
> 这些是 CMake 中一些非常基础且重要的概念和命令。随着经验的增长，你可能会遇到更多高级特性和用法。学习 CMake 的最佳方式是通过实践，不断尝试新的功能并参考官方文档。
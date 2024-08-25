# CPlusplus_graphics
目标：
1. 使用现有的图形库，能够编写控制台 + 基于图形化的 C++程序代码
2. 能够看懂图形库的代码，针对游戏程序/动画程序/三维重建 优化下图形库

参考库：
1. https://github.com/ocornut/imgui 
2. https://en.cppreference.com/w/cpp/links/libs  找sfml，放弃了基于C语言完成的SDL库（https://github.com/libsdl-org/SDL）。
3. https://www.sfml-dev.org/ ，代码：https://github.com/SFML/SFML/tree/master
4. glfw:https://github.com/glfw/glfw,文档：https://www.glfw.org/docs/latest/quick.html
5. CMakeLists.txt 语法
https://blog.csdn.net/afei__/article/details/81201039   上文讲的很详细，可认真学习下。https://www.bilibili.com/video/BV1fy4y1b7TC
上面 xiao bing 老师的视频讲的很详细，收获超级大
6. 游戏参考：参考童晶老师
    -  https://codebus.cn/funcoding/
    - 

## 任务1 ： 基于图形库，扩充下C++代码样例
### 安装ImGui库，运行带界面的“hello world”
#### windows + mingw + vscode

ImGui的目录结构如下：
imgui/
- backends/ 后端文件夹，包含了不同平台和渲染器的实现代码
- examples/ 示例文件夹，包含了各种使用ImGui的示例程序
- misc/ 杂项文件夹，包含了一些辅助工具和扩展模块
- imconfig.h 配置文件，可以用来修改ImGui的一些默认设置
- imgui.cpp/imgui.h ImGui的核心源代码，必须添加到你的项目中
- imgui_demo.cpp/imgui_demo.h ImGui的演示源代码，包含了各种控件和窗口的示例代码
- imgui_draw.cpp/imgui_draw.h ImGui的绘制源代码，负责渲染各种图形元素
- imgui_internal.h ImGui的内部头文件，包含了一些高级功能和实现细节
- imgui_tables.cpp/imgui_tables.h ImGui的表格源代码，提供了创建和管理表格的功能
- imgui_widgets.cpp/imgui_widgets.h ImGui的控件源代码，提供了创建和管理各种控件的功能
- imstb_rectpack.h/imstb_textedit.h/imstb_truetype.h 第三方库文件，用于矩形打包、文本编辑和字体渲染

使用cmake完成编译链接和运行，具体的指令如下：
1.	Configuring and Building the System:
```sh
cmake -S . -B ./build -G "MinGW Makefiles"

说明：This command configures the build system using CMake, specifying the source directory (-S .), the build directory (-B ./build), and the generator (-G "MinGW Makefiles").

2. compiling and linking  the project:

cmake --build ./build

参考资料：
https://blog.csdn.net/sq8706/article/details/139100617?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EYuanLiJiHua%7ECtr-1-139100617-blog-136861672.235%5Ev43%5Epc_blog_bottom_relevance_base1&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EYuanLiJiHua%7ECtr-1-139100617-blog-136861672.235%5Ev43%5Epc_blog_bottom_relevance_base1&utm_relevant_index=2


#### macos + gcc + vscode + cmake + imgui

1. 需要用brew install 安装gcc，cmake，以及glfw，否则库的版本不同意
2. 最重要的是CMakelist.txt
3. 执行cmake的编译命令如下

rm -rf build
mkdir build
cd build
cmake ..
cmake --build .
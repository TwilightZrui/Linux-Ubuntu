<!--
 * @Author: YourName
 * @Date: 2022-08-25 16:42:31
 * @LastEditTime: 2022-09-22 11:34:47
 * @LastEditors: YourName
 * @Description:
 * @FilePath: /Linux-Ubuntu/Vscode.md
 * 版权声明
-->

### TODO + TODO Tree

[TODO highligh](https://blog.csdn.net/weixin_42268975/article/details/106021808)

### vscode中取消conda激活环境

setting.json中添加：

```bash
"python.terminal.activateEnvironmen":false,
```

### Vscode ROS单个节点调试方法

[ROS单个节点调试方法](https://blog.csdn.net/weixin_42098782/article/details/109265910?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-109265910-blog-123603717.pc_relevant_multi_platform_whitelistv1&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-109265910-blog-123603717.pc_relevant_multi_platform_whitelistv1)

### ROS vscode调试

```bash
launch-prefix="gdb -ex run --args"
<node pkg="waypoint_follower" type="pure_persuit" name="pure_pursuit" output="screen" launch-prefix="xterm -e gdb -ex run --args">
        <param name="is_linear_interpolation" value="$(arg is_linear_interpolation)"/>
```

### Vscode remote

[VsCode通过SSH连接远程服务器开发](https://www.cnblogs.com/chnmig/p/12160248.html)

### 快捷键

### * **`Ctrl + Tab`**  可以列出最近打开的文件，在开发时，两个文件间切换时效率很高

* ctrl ` ：打开terminator
* Ctrl + :进入设置界面
* ctrl shit + e :文件
* ctrl + b:关闭侧栏
* ctrl shit + p:快速打开setting
* ctrl e :查找文件
* Ctrl+Shift+I选择ros: 提供ros代码对齐
* ctrl + shif + b: 快捷键编译
* `Ctrl + Tab`, 可以列出最近打开的文件，在开发时，两个文件间切换时效率很高。
* ctrl + 键盘箭头：停靠
* ctrl+alt+t koroFileHeader生成 函数注释
* ctrl+commond+i 头部注释
* ctrl+commond+t 函数注释

### 设置

* open workspace settings: workbench.editor.wrapTabs，勾选该设置项即可 所有文件都展开
* Better Align: 使用方法：Ctrl+Shift+p输入“Align”确认即可。

[TODO highligh](https://blog.csdn.net/weixin_42268975/article/details/106021808)

### 插件

#### Git

Git graph

Trailing Spaces，该插件会将行尾空格高亮。
koroFileHeader VSCode自动添加注释

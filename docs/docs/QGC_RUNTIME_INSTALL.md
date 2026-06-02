# QGroundControl 在 Jetson TX1 上的运行安装方式

本文记录本项目中 QGroundControl 在 Jetson TX1 手持终端上的运行布局和启动方式。

## 运行目录布局

启动脚本默认使用以下路径：

```text
/opt/qgroundcontrol/QGroundControl
/opt/qgroundcontrol/qgroundcontrol.png
/home/jetson/.local/bin/qgroundcontrol
/home/jetson/Desktop/qgroundcontrol.desktop
安装 QGroundControl 二进制
将已经编译好的 ARM64 QGroundControl 二进制复制到 /opt/qgroundcontrol：

sudo mkdir -p /opt/qgroundcontrol
sudo cp QGroundControl /opt/qgroundcontrol/QGroundControl
sudo chmod +x /opt/qgroundcontrol/QGroundControl
如果有图标文件：

sudo cp qgroundcontrol.png /opt/qgroundcontrol/qgroundcontrol.png
安装启动脚本
mkdir -p ~/.local/bin
cp qgc/launcher/qgroundcontrol ~/.local/bin/qgroundcontrol
chmod +x ~/.local/bin/qgroundcontrol
启动脚本里包含 TX1 上运行 QGC 所需的 Qt/Tegra 修正，例如：

QT_XCB_GL_INTEGRATION=xcb_glx
QSG_RENDER_LOOP=basic
QML_BAD_GUI_RENDER_LOOP=1
QT_PLUGIN_PATH=/usr/lib/aarch64-linux-gnu/qt5/plugins
QML2_IMPORT_PATH=/usr/lib/aarch64-linux-gnu/qt5/qml
这些设置用于减少 TX1 上 Qt Quick / Tegra 图形初始化问题，例如黑屏、窗口无法显示或渲染线程卡死。

安装桌面启动项
cp qgc/desktop/qgroundcontrol.desktop ~/Desktop/
chmod +x ~/Desktop/qgroundcontrol.desktop
gio set ~/Desktop/qgroundcontrol.desktop metadata::trusted true
如果桌面没有立即刷新，可以注销并重新登录图形界面。

启动 QGroundControl
终端启动：

qgroundcontrol
或者双击桌面上的 QGroundControl 图标。

全屏说明
启动脚本默认使用：

/opt/qgroundcontrol/QGroundControl --fullscreen
这是因为手持 TX1 终端屏幕较小，全屏可以避免标题栏和窗口边框占用空间，导致 QGC 控件显示不完整。


页面下方提交信息写：

```text
Add QGroundControl runtime install guide
仍然选择：

Commit directly to the main branch.
然后点：

Commit changes

# QGroundControl 二进制产物说明

本仓库没有直接提交已经编译好的 QGroundControl ARM64 二进制文件。

建议把 TX1 上编译出的 QGroundControl 二进制作为 GitHub Release 附件发布，而不是直接提交到 main 分支。

## 适用环境

```text
Architecture: aarch64
OS: Ubuntu 20.04.6 LTS
Kernel: 4.9.337-tegra
L4T: R32.7.6
Qt: Ubuntu 20.04 arm64 Qt5 packages
```

## 为什么不直接提交二进制

- 它是构建产物；
- 它只适用于特定 TX1 / ARM64 环境；
- 会增加仓库体积；
- patch 和构建说明更容易审查；
- GitHub Release 更适合发布二进制附件。

## 已记录的信息

二进制相关信息记录在：

```text
qgc/artifacts-info/qgroundcontrol-runtime-info.txt
```

其中包含文件大小、ELF 架构、SHA256 校验值、动态依赖、启动脚本和桌面项信息。

## TX1 上的默认安装路径

```text
/opt/qgroundcontrol/QGroundControl
```

具体安装方式见：

```text
docs/QGC_RUNTIME_INSTALL.md
```

# Handheld Jetson TX1 Development Terminal for PX4 / QGroundControl

This project documents a handheld NVIDIA Jetson TX1 development terminal used for PX4 flight-controller debugging and QGroundControl development.

## 中文简介

本项目记录了一款基于 NVIDIA Jetson TX1 的手持式开发终端。该终端保留 Jetson Linux / L4T R32.7.x 底层支持，将 Ubuntu 用户态升级到 20.04，并在其上编译、安装和运行 QGroundControl，用于 PX4 飞控调试、MAVLink telemetry 查看、参数调试、USB / 串口 / UDP 链路测试以及现场地面站验证。

The terminal is based on:

- NVIDIA Jetson TX1
- Ubuntu 20.04 userland
- Jetson Linux / L4T R32.7.x kernel and BSP retained
- custom-built QGroundControl running natively on ARM64
- GPIO / I2C / USB / serial / network debugging support

## Main Use Case

```text
Jetson TX1 handheld terminal
  -> build and run QGroundControl on ARM64
  -> connect PX4 flight controller through USB / serial / UDP / telemetry radio
  -> inspect MAVLink telemetry
  -> tune PX4 parameters
  -> validate custom ground-station behavior
```

## Repository Contents

```text
docs/
  System and build notes collected from the target TX1

qgc/patches/
  Local QGroundControl changes exported as patch files

qgc/launcher/
  Installed launcher script used on the TX1

qgc/desktop/
  Desktop launcher used on the TX1

qgc/artifacts-info/
  File, ldd and checksum information for the compiled QGroundControl binary
  docs/QGC_RUNTIME_INSTALL.md
  Runtime installation layout and launcher setup for QGroundControl on TX1
  
qgc/artifacts-info/BINARY_ARTIFACT.md
  Notes about the compiled ARM64 QGroundControl binary and GitHub Release publishing
```

## About the QGroundControl Source

The full QGroundControl source tree was not copied into this repository because it is a large upstream project with submodules and build artifacts. The practical and GitHub-friendly workflow is:

1. Clone upstream QGroundControl.
2. Check out the recorded base commit.
3. Initialize submodules.
4. Apply the exported patch from `qgc/patches/`.
5. Build on the Jetson TX1 or another compatible ARM64 environment.

See `docs/QGC_BUILD_AND_EXPORT_NOTES.md` for details.
## Reproduce QGroundControl Source State

Clone upstream QGroundControl and check out the recorded base commit:

```bash
git clone https://github.com/mavlink/qgroundcontrol.git
cd qgroundcontrol
git checkout 495a17b4964d3ed90f241388b3a02a35e96c9663
git submodule update --init --recursive

Do not upload the full `/home/jetson/qgroundcontrol` directory directly to GitHub. The local source tree includes upstream QGroundControl history, submodule repositories, and build artifacts. In this project, local changes are exported as patches under `qgc/patches/`, which is a cleaner and more reproducible way to publish the TX1-specific work.

## Binary Artifact

The compiled TX1 ARM64 QGroundControl binary is intentionally not included in the GitHub upload folder. It is recorded in `qgc/artifacts-info/` and can be kept locally or attached to a GitHub Release if desired.

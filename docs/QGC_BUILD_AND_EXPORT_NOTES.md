# QGroundControl Build and Export Notes

This file records the QGroundControl source state and build/runtime information from the Jetson TX1.

## Recommended GitHub Strategy

Do not upload the complete upstream QGroundControl source tree with `.git`, submodules and build artifacts.

Recommended options:

1. Fork upstream QGroundControl and push the local changes as commits.
2. Keep this project as the handheld TX1 terminal documentation repository and store QGC changes as patches.
3. Attach compiled binaries to GitHub Releases instead of committing them to the repository.

## Source Tree

```text
path=/home/jetson/qgroundcontrol
1.4G	/home/jetson/qgroundcontrol
```

## Git State

```text
origin	https://github.com/mavlink/qgroundcontrol.git (fetch)
origin	https://github.com/mavlink/qgroundcontrol.git (push)
commit 495a17b4964d3ed90f241388b3a02a35e96c9663
Author:     Julian Oes <julian@oes.ch>
AuthorDate: Mon Dec 2 15:56:05 2024 +1300
Commit:     Julian Oes <julian@oes.ch>
CommitDate: Mon Dec 2 15:56:34 2024 +1300

    CI: remove yet another Android platform we don't want

== status ==
 m libs/shapelib
 M src/AutoPilotPlugins/PX4/SensorsSetup.qml
 M src/Camera/QGCCameraControl.cc
 M src/FactSystem/FactMetaData.cc
 M src/FactSystem/ParameterManager.cc
 M src/FirmwarePlugin/APM/APMFirmwarePlugin.cc
 ? src/FirmwarePlugin/APM/ArduPilot-Parameter-Repository
 M src/LogCompressor.cc
 M src/MissionManager/MissionCommandUIInfo.cc
 M src/MissionManager/QGCMapPolygon.cc
 M src/MissionManager/QGCMapPolyline.cc
 M src/MissionManager/SurveyComplexItem.cc
 M src/PositionManager/PositionManager.cpp
 M src/QGCComboBox.cc
 M src/QGCFileDownload.cc
 M src/QmlControls/ParameterEditorController.cc
 M src/QmlControls/ParameterEditorDialog.qml
 M src/QmlControls/QGCSimpleMessageDialog.qml
 M src/QmlControls/QGroundControlQmlGlobal.cc
 M src/QmlControls/SliderSwitch.qml
 M src/QtLocationPlugin/GoogleMapProvider.cpp
 M src/QtLocationPlugin/QGCMapTileSet.cpp
 M src/QtLocationPlugin/QGCTileCacheWorker.cpp
 M src/Settings/AppSettings.cc
 M src/Terrain/TerrainQuery.cc
 M src/comm/SerialLink.cc
 M src/comm/TCPLink.cc

== modified files ==
M	libs/shapelib
M	src/AutoPilotPlugins/PX4/SensorsSetup.qml
M	src/Camera/QGCCameraControl.cc
M	src/FactSystem/FactMetaData.cc
M	src/FactSystem/ParameterManager.cc
M	src/FirmwarePlugin/APM/APMFirmwarePlugin.cc
M	src/FirmwarePlugin/APM/ArduPilot-Parameter-Repository
M	src/LogCompressor.cc
M	src/MissionManager/MissionCommandUIInfo.cc
M	src/MissionManager/QGCMapPolygon.cc
M	src/MissionManager/QGCMapPolyline.cc
M	src/MissionManager/SurveyComplexItem.cc
M	src/PositionManager/PositionManager.cpp
M	src/QGCComboBox.cc
M	src/QGCFileDownload.cc
M	src/QmlControls/ParameterEditorController.cc
M	src/QmlControls/ParameterEditorDialog.qml
M	src/QmlControls/QGCSimpleMessageDialog.qml
M	src/QmlControls/QGroundControlQmlGlobal.cc
M	src/QmlControls/SliderSwitch.qml
M	src/QtLocationPlugin/GoogleMapProvider.cpp
M	src/QtLocationPlugin/QGCMapTileSet.cpp
M	src/QtLocationPlugin/QGCTileCacheWorker.cpp
M	src/Settings/AppSettings.cc
M	src/Terrain/TerrainQuery.cc
M	src/comm/SerialLink.cc
M	src/comm/TCPLink.cc

== submodules ==
 aa3c67c59160715216e89ae2c48291d6021601fa libs/OpenSSL/android_openssl (1.1.1l_1.0.2u)
 0fd6b4f71dd85b2009ee4d1aeb296e2c11fc9d68 libs/eigen (3.3.9)
 59f7f5c0ec2e76fadbc1dc40cc0705d614472edc libs/libevents/libevents (59f7f5c)
 bc889afb4c5bf1c0d8ee29ef35eaaf4c8bef8a5d libs/libevents/libevents/libs/cpp/parse/nlohmann_json (v3.11.2)
 55988d1ec99761b9c5e447a51dcb258161672805 libs/mavlink/include/mavlink/v2.0 (55988d1e)
 bcae73281fd29ab8e7a41fc3246223b15d44d0df libs/qmdnsengine (0.2.0-15-gbcae732)
 b0caadca11ecf7a54139d37bced91b1cd0347cf3 libs/qmlglsink/gst-plugins-good (1.16.0-299-gb0caadca1)
 6189dbd83ba2382fe0ebbc8f2308e582832c93fa libs/shapelib (v1.5.0-67-g6189dbd)
 090e6a054d6283b144d20f5783852b95eade90ee libs/xz-embedded (heads/master)
 772370ab665fd7a7edcfe488f1c900a1d7d3a4a9 src/FirmwarePlugin/APM/ArduPilot-Parameter-Repository (772370a)
 a41210ede8c2d22dd8e9fdcf388fca927c1fc5e1 src/GPS/Drivers (remotes/origin/backport-release/1.13-52-ga41210e)
```

## Build Cache Summary

```text
CMAKE_BUILD_TYPE:STRING=Release
CMAKE_CXX_COMPILER:FILEPATH=/usr/bin/c++
CMAKE_CXX_COMPILER_AR:FILEPATH=/usr/bin/gcc-ar-9
CMAKE_CXX_COMPILER_RANLIB:FILEPATH=/usr/bin/gcc-ranlib-9
CMAKE_C_COMPILER:FILEPATH=/usr/bin/cc
CMAKE_C_COMPILER_AR:FILEPATH=/usr/bin/gcc-ar-9
CMAKE_C_COMPILER_RANLIB:FILEPATH=/usr/bin/gcc-ranlib-9
CMAKE_INSTALL_PREFIX:PATH=/usr/local
QGC_GST_MICROHARD_ENABLED:BOOL=OFF
QGC_GST_TAISYNC_ENABLED:BOOL=OFF
Qt5Bluetooth_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Bluetooth
Qt5Charts_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Charts
Qt5Concurrent_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Concurrent
Qt5Core_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Core
Qt5Gui_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Gui
Qt5Location_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Location
Qt5Multimedia_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Multimedia
Qt5Network_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Network
Qt5OpenGL_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5OpenGL
Qt5PositioningQuick_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5PositioningQuick
Qt5Positioning_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Positioning
Qt5Qml_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Qml
Qt5QuickControls2_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5QuickControls2
Qt5QuickWidgets_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5QuickWidgets
Qt5Quick_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Quick
Qt5SerialPort_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5SerialPort
Qt5Sql_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Sql
Qt5Svg_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Svg
Qt5Test_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Test
Qt5TextToSpeech_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5TextToSpeech
Qt5Widgets_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Widgets
Qt5X11Extras_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5X11Extras
Qt5Xml_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5Xml
Qt5_DIR:PATH=/usr/lib/aarch64-linux-gnu/cmake/Qt5
CMAKE_BUILD_TYPE-STRINGS:INTERNAL=Debug;Release;RelWithDebInfo;MinSizeRel;Coverage
CMAKE_CXX_COMPILER-ADVANCED:INTERNAL=1
CMAKE_CXX_COMPILER_AR-ADVANCED:INTERNAL=1
CMAKE_CXX_COMPILER_RANLIB-ADVANCED:INTERNAL=1
CMAKE_C_COMPILER-ADVANCED:INTERNAL=1
CMAKE_C_COMPILER_AR-ADVANCED:INTERNAL=1
CMAKE_C_COMPILER_RANLIB-ADVANCED:INTERNAL=1
```

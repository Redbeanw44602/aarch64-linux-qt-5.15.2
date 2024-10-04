# aarch64-linux-qt

> ver. **5.15.2**

*Out-of-the-box qt libraries for cross-compilation toolchains.*

Module |
-|
qtwebsockets |
qtsvg |
qtwayland |
qtdeclarative |
qtconnectivity |
qtmultimedia |
qtlottie |

## how to use with xmake

 - Download the release and unpack it to your preferred location, such as `/home/yourname/qt-5.15.2-aarch64`
 - Xmake tries to use qmake to find the installation path of qt, so we need to build a fake qmake. Use the following command, please replace `<YOUR_QT_DIR>` with your own
```
g++ -fmax-errors=1 -o qmake -D"PREFIX=\"<YOUR_QT_DIR>\"" qmake.cpp
```
 - Test the output of qmake, if everything is OK:
```
> ./qmake
QT_VERSION:5.15.2
QT_INSTALL_BINS:/home/yourname/qt-5.15.2-aarch64/bin
QT_INSTALL_LIBS:/home/yourname/qt-5.15.2-aarch64/lib
QT_INSTALL_HEADERS:/home/yourname/qt-5.15.2-aarch64/include
QT_INSTALL_QML:/home/yourname/qt-5.15.2-aarch64/lib/qt/qml
QT_INSTALL_PREFIX:/home/yourname/qt-5.15.2-aarch64
```
 - Manually specify the `qt` path when configuring, and don't forget to select the cross toolchain!
```
xmake f --cross="aarch64-linux-gnu-" --qt="/home/yourname/qt-5.15.2-aarch64"
```

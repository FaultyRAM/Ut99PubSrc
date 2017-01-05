# Unreal Tournament v432 Public Source Distribution

This is the publically-released portion of the Unreal Tournament '99 source
code. It has been ported to [CMake](https://cmake.org) and fixed for modern
C++ compiler toolchains.

## Prerequisites

### Windows

* Windows SDK (using a Windows XP toolset is supported)
* MFC (required by Setup)
* DirectX 7-compatible headers and libraries (required by D3DDrv and Setup)

### Linux

* GCC 2.95.x (GCC 3.x and later are ABI incompatible)
* X11 (required by XDrv, XMesaGLDrv and XLaunch)
* OpenGL (required by XMesaGLDrv)

*NB: The Linux build has not been tested. Use at your own risk.*

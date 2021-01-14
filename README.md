# GS+ Intro & Usage
GS+ is an Apple IIgs emulator derived from GSport, which itself is based on KEGS. Although GS+ can be launched without command-line arguments, there are several command-line arguments that are especially helpful. For example, -resizeable launches emulator in a resizable window. For a full list of optional flags, pass -h to the emulator, e.g. ./GSplus -h.

Once you have started the emulator, F4 is used to configure ROM and disk locations and MUCH more.

# Build instructions

## OS X dependencies
    brew install cmake pkg-config re2c sdl2 sdl2_image freetype

## Linux dependencies
    apt-get install re2c libsdl2-dev libsdl2-image-dev libfreetype6-dev libpcap0.8-dev

## WIN32 dependencies
Install MSYS2 (not MSYS, not cygwin)

32-bit build:

    pacman  -S re2c mingw-w64-i686-cmake mingw-w64-i686-SDL2 mingw-w64-i686-SDL2_image mingw-w64-i686-freetype

64-bit build:

    pacman  -S re2c mingw-w64-x86_64-cmake mingw-w64-x86_64-SDL2 mingw-w64-x86_64-SDL2_image mingw-w64-x86_64-freetype


## Linux, OS X, build
    mkdir build
    cd build
    cmake .. -DWITH_RAWNET=ON
    (optionally: ccmake .. to configure stuff)
    make


## Windows Build

### mingw SDL build
    mkdir build
    cd build
    cmake ../ -DDRIVER=SDL2 -DWITH_DEBUGGER=OFF -G "MSYS Makefiles"
    make GSplus.exe
### mingw GDI build

    mkdir build
    cd build
    cmake ../ -DDRIVER=WIN32 -DWITH_DEBUGGER=OFF -G "MSYS Makefiles"
    make GSplus.exe

WINDOWS BUILD NOTES
====================

Some notes on how to build Arena Core for Windows.

Most developers use cross-compilation from Ubuntu to build executables for
Windows. This is also used to build the release binaries.

Building on Windows itself is possible (for example using msys / mingw-w64),
but no one documented the steps to do this. If you are doing this, please contribute them.

Cross-compilation
-------------------

These steps can be performed on, for example, an Ubuntu VM. The depends system
will also work on other Linux distributions, however the commands for
installing the toolchain will be different.

First install the toolchains:

    sudo apt-get install g++-mingw-w64-i686 mingw-w64-i686-dev g++-mingw-w64-x86-64 mingw-w64-x86-64-dev

To build executables for Windows 32-bit:

    cd depends
    chmod 755 *
    make HOST=i686-w64-mingw32 -j4
    cd ..
    bash ./autogen.sh
    ./configure --prefix=`pwd`/depends/i686-w64-mingw32
    OR
    CONFIG_SITE=$PWD/depends/i686-w64-mingw32/share/config.site ./configure --prefix=/
    chmod 777 ./share/genbuild.sh
    make

To build executables for Windows 64-bit:

    cd depends
    chmod 755 *
    make HOST=x86_64-w64-mingw32 -j4
    cd ..
    bash ./autogen.sh
    ./configure --prefix=`pwd`/depends/x86_64-w64-mingw32
    chmod 777 ./share/genbuild.sh
    make

For further documentation on the depends system see [README.md](../depends/README.md) in the depends directory.

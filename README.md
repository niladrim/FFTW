# FFTW
FFT implementation using fftw library
g++ `Magick++-config --cxxflags --cppflags` -L/usr/local/lib/ -I/usr/local/include/ -O0 -Wall -o fourier main.cpp `Magick++-config --ldflags --libs` -lfftw3 -lm

#!/bin/sh
  2 # FourierTest/build.sh
  3 # Compiles fftw3 for Android
  4 # Make sure you have NDK_ROOT defined in .bashrc or .bash_profile
  5
  6 INSTALL_DIR="`pwd`/jni/fftw3"
  7 SRC_DIR="`pwd`/../fftw-3.3.4"
  8 NDK_ROOT="/home/n.mukherjee/android-ndk-r10e"
  9
 10 cd $SRC_DIR
 11
 12 export
 13 PATH="$NDK_ROOT/toolchains/arm-linux-androideabi-4.9/prebuilt/linux-x86_64/bin/:$PATH"
 14 export SYS_ROOT="$NDK_ROOT/platforms/android-9/arch-arm/"
 15 export CC="arm-linux-androideabi-gcc --sysroot=$SYS_ROOT -mfloat-abi=softfp -mfpu=neon"
 16 export LD="arm-linux-androideabi-ld"
 17 export AR="arm-linux-androideabi-ar"
 18 export RANLIB="arm-linux-androideabi-ranlib"
 19 export STRIP="arm-linux-androideabi-strip"
 20
 21
 22 mkdir -p $INSTALL_DIR
 23 ./configure --host=arm-linux-gnueabi --build=i686-pc-linux-gnu --enable-float --enable-neon --prefix=$INSTALL_DIR LIBS="-lc -lgcc" ARM_FLOAT_ABI=softfp
 24
 25 make
 26 make install
 27
 28 exit 0



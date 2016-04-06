# FFTW
FFT implementation using fftw library
g++ `Magick++-config --cxxflags --cppflags` -L/usr/local/lib/ -I/usr/local/include/ -O0 -Wall -o fourier main.cpp `Magick++-config --ldflags --libs` -lfftw3 -lm


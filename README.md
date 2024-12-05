`libuvc` is a cross-platform library for USB video devices, built atop `libusb`.
It enables fine-grained control over USB video devices exporting the standard USB Video Class
(UVC) interface, enabling developers to write drivers for previously unsupported devices,
or just access UVC devices in a generic fashion.


## Ed: building libuvc from the Tiliter windows machine: 

Download binaries for:
- pthreads
- libusb

    git clone https://github.com/stolmen/libuvc
    cd libuvc
    mkdir build
    cd build
    cmake .. -DPTHREADS_WIN_INCLUDE_DIR=/c/Users/DemoS/Downloads/pthreads-w32-2-9-1-release/Pre-built.2/include -DPTHREADS_WIN_IMPORT_LIB_PATH=/c/Users/DemoS/Downloads/pthreads-w32-2-9-1-release/Pre-built.2/lib/x86/pthreadVC2.lib -DLIBUSB_WIN_INCLUDE_DIR=/c/Users/DemoS/Downloads/libusb-1.0.27/include -DLIBUSB_WIN_IMPORT_LIB_PATH=/c/Users/DemoS/Downloads/libusb-1.0.27/VS2017/MS32/static/libusb-1.0.lib
    nmake # this may not work in which case you can open the project files built by cmake in Visual Studio and build from there.

## Getting and Building libuvc

Prerequisites: You will need `libusb` and [CMake](http://www.cmake.org/) installed.

To build, you can just run these shell commands:

    git clone https://github.com/libuvc/libuvc
    cd libuvc
    mkdir build
    cd build
    cmake ..
    make && sudo make install

and you're set! If you want to change the build configuration, you can edit `CMakeCache.txt`
in the build directory, or use a CMake GUI to make the desired changes.

There is also `BUILD_EXAMPLE` and `BUILD_TEST` options to enable the compilation of `example` and `uvc_test` programs. To use them, replace the `cmake ..` command above with `cmake .. -DBUILD_TEST=ON -DBUILD_EXAMPLE=ON`.
Then you can start them with `./example` and `./uvc_test` respectively. Note that you need OpenCV to build the later (for displaying image).

## Developing with libuvc

The documentation for `libuvc` can currently be found at https://libuvc.github.io/.

Happy hacking!

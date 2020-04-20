# Compiling μTox from source

Without dying in the try™ Edition

Disclaimer: this process or software comes with no warranty. <br />
Note: This guide can be followed and done with the **Windows XP SP3** operating system.
<br />
<br />

## Building a 64 bit binary

### Software required

We will mainly use two developer utilities called **MinGW** and **CMake GUI**. Files needed are:

- [CMake GUI installer](https://github.com/blueclouds8666/uTox_XP/raw/files/utilities/cmake-3.2.3-win32-x86.exe)
- [MinGW Portable](https://github.com/blueclouds8666/uTox_XP/raw/files/utilities/MinGW-portable.7z)
- [MinGW component - GCC Compiler x64](https://github.com/blueclouds8666/uTox_XP/raw/files/utilities/MinGW%20Packages%20x64/mingw-w64-x86_64-7.1.0-release-win32-seh-rt_v5-rev2.7z)
- [MinGW component - package configurator x64](https://github.com/blueclouds8666/uTox_XP/raw/files/utilities/MinGW%20Packages%20x64/mingw-w64-x86_64-pkg-config-0.29-1-any.pkg.tar.xz)

1. Install CMake GUI with default values from *cmake-3.2.3-win32-x86.exe*.
2. Extract *MinGW-portable.7z* on the C:\ root folder. A new folder C:\MinGW will appear.
3. Now you will need to install the MinGW components, the ones starting by *mingw-w64-*. <br />
  3.1. To install these components, open each compressed file and extract **the content of the mingw64** folder to C:\MinGW
4. Dev software is now installed. Now navigate to C:\MinGW\msys\1.0 and make a new folder called *project*
<br />

### Preparing μTox source files

Now we will need the μTox source files, plus the precompiled libraries. Those are:

- [uTox source code](https://github.com/blueclouds8666/uTox_XP/archive/develop.zip)
- [uTox library - filter_audio x64](https://github.com/blueclouds8666/uTox_XP/raw/files/libraries-precompiled/windows-x64/libfilteraudio_build_windows_x86-64.zip)
- [uTox library - OpenAL x64](https://github.com/blueclouds8666/uTox_XP/raw/files/libraries-precompiled/windows-x64/libopenal-1.16.0_build_windows_x86-64.zip)
- [uTox library - Opus x64 v1.3.1](https://github.com/blueclouds8666/uTox_XP/raw/files/libraries-precompiled/windows-x64/libopus-1.3.1_build_windows_x86-64.zip)
- [uTox library - libsodium x64 v1.0.18](https://github.com/blueclouds8666/uTox_XP/raw/files/libraries-precompiled/windows-x64/libsodium-1.0.18_build_windows_x86-64.zip)
- [uTox library - c-toxcore x64 v0.2.11](https://github.com/blueclouds8666/uTox_XP/raw/files/libraries-precompiled/windows-x64/libtoxcore-toktok-only-0.2.11_build_windows_x86-64.zip)
- [uTox library - VPX x64 v1.8.2](https://github.com/blueclouds8666/uTox_XP/raw/files/libraries-precompiled/windows-x64/libvpx-1.8.2_build_windows_x86-64.zip)
- [uTox third party lib - stb](https://github.com/blueclouds8666/uTox_XP/raw/files/third-party%20libraries/stb-9d9f75eb682dd98b34de08bb5c489c6c561c9fa6.zip)
- [uTox third party lib - minIni](https://github.com/blueclouds8666/uTox_XP/raw/files/third-party%20libraries/minIni-77908366d4c0a758e33c4c6f39a29eba836ae7dd.zip)
- [uTox third party lib - QR Code generator](https://github.com/blueclouds8666/uTox_XP/raw/files/third-party%20libraries/QR-Code-generator-7e18dfe885f1cf2924078542927496c35d575ce7.zip)

5. Extract the μTox source code on C:\MinGW\msys\1.0\project
6. Rename the resulting folder to "uTox"
7. Browse to \project\uTox\libs\windows and extract there the six μtox libraries.
8. Browse to \project\uTox\third-party and extract there the three third-party libs.
<br />

### Final steps

9. Open CMake GUI. It can be found at Start menu > All programs > CMake
10. Fill these gaps as following:

> - *Where is the source code:* C:/MinGW/msys/1.0/project/uTox
> - *Where to build the binaries:* C:/MinGW/msys/1.0/project/uTox/build

11. Click on generate. A new window will pop up, set the values as:

> - *Generator for this project:* MinGW Makefiles
> - *From the list below:* Specify native compilers

12. After clicking next, you will only need to define the C compiler path, which is: C:/MinGW/bin/x86_64-w64-mingw32-gcc.exe
13. Hit finish. If no errors show up, it means you did everything right, congratulations!
14. You can now compile the binary by running \project\uTox\build\buildWindows.bat. After the compiler finishes, you should get a binary EXE file on the same folder. Now it's time to enjoy μTox!
15. Several compiler options can be tweaked from the CMake panel. Make sure to click on Generate after you change them.
<br />
<br />

### Compiling SeroCoin

## Windows

##### Windows Dependencies

You can build for 32-bit or 64-bit Windows. **If you're not sure, pick 64-bit.**

-   Download the [Build Tools for Visual Studio 2019](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) Installer
-   When it opens up select **C++ build tools**, it automatically selects the needed parts. Make sure **MSVC v141 Build Tools** is selected.
-   Install Boost. Select the appropriate version for your system:
    -   [Boost 64-bit](https://bintray.com/boostorg/release/download_file?file_path=1.69.0%2Fbinaries%2Fboost_1_69_0-msvc-14.1-64.exe)
    -   [Boost 32-bit](https://bintray.com/boostorg/release/download_file?file_path=1.69.0%2Fbinaries%2Fboost_1_69_0-msvc-14.1-32.exe)
-   Install the latest full LTS version of OpenSSL (currently OpenSSL 1.1.1j). Select the appropriate version for your system:
    -   [OpenSSL 64-bit](https://slproweb.com/download/Win64OpenSSL-1_1_1j.exe)
    -   [OpenSSL 32-bit](https://slproweb.com/download/Win32OpenSSL-1_1_1j.exe)

##### Windows with VS2019

For 64-bit:

-   From the start menu, open **x64 Native Tools Command Prompt for VS 2019**.
-   `cd <your_serocoin_directory>`
-   `mkdir build`
-   `cd build`
-   `cmake -G "Visual Studio 16 2019" -A x64 .. -DBOOST_ROOT=C:/local/boost_1_69_0`
-   `MSBuild SeroCoin.sln /p:Configuration=Release /p:PlatformToolset=v141 /m` or `MSBuild src\cli.vcxproj /p:Configuration=Release /p:PlatformToolset=v141 /m`

For 32-bit:

-   From the start menu, open **x86 Native Tools Command Prompt for VS 2019**.
-   `cd <your_serocoin_directory>`
-   `mkdir build`
-   `cd build`
-   `cmake -G "Visual Studio 16 2019" -A Win32 .. -DBOOST_ROOT=C:/local/boost_1_69_0`
-   `MSBuild SeroCoin.sln /p:Configuration=Release /p:Platform=Win32 /p:PlatformToolset=v141 /m`

The binaries will be in the `src/Release` folder when you are complete.

-   `cd src`
-   `cd Release`
-   `SeroCoind.exe --version`


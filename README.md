# websocketpp-x86_x64
Native Visual Studio solution/project files to compile in Windows x86/x64/Release/Debug

# Background #
websocketpp provides a CMake-based build solution. This, in Windows,
is not easy to use because of its inability to find dependencies
easily and the quality of project/solution files that it generates. I
have tried to remove all the extraneous junk and concentrate on
Win32/x64/Release/Debug, with static libraries and DLL run-times.

# Installation #

  * git clone [websocketpp, tested w/ v0.8.1](https://github.com/zaphoyd/websocketpp)
  * git clone [websocketpp-x86_x64](https://github.com/sridharb1/websocketpp-x86_x64)
    to another folder
  * Copy the build folder downloaded above to the root of the websocketpp
    source tree.

# Note #

To compile websocketpp, you need 

  * [zlib, tested w/ v1.2.11](https://github.com/madler/zlib)
  * Use my [zlib-x86_x64](https://github.com/sridharb1/zlib-x86_x64) to compile zlib on Windows.
  * [OpenSSL, tested w/ v1.1.1g-DEV](https://github.com/openssl/openssl)
  * You can use my [openssl-x86_x64](https://github.com/sridharb1/openssl-x86_x64) to compile openssl on Windows.
  * boost c++ libraries. See how to fetch and compile boost below.

## Fetching and compiling boost ##

  * Get the latest boost (I used v1.72). Instructions available at [Boost with git](https://github.com/boostorg/wiki/wiki/Getting-Started%3A-Overview)
  * My projects follow this heirarchy. I keep all the projects in the
    same level, for e.g. zlib is in E:\Projects\zlib, websocketpp is
    in E:\Projects\websocketpp etc. boost sources would be in
    E:\Projects\Boost.
  * See below for concise instructions on fetching and compiling boost
    with Visual Studio.
  * The last command below installs boost headers and libraries in
    E:\Boost. These projects refer to this relative path (i.e. the
    installed boost is in one level higher than the Projects folder).
  * This command uses toolset=msvc-14.2 (aka VS 2019). As newer
    versions come, please adjust accordingly. Please refer to [Boost Toolsets](https://boostorg.github.io/build/manual/develop/index.html).
  * This builds static boost libraries for x86/x64/Release/Debug with
    CRT DLL runtimes. This is the combination that I use in all my
    projects.

  ``` shell
  git clone --recursive https://github.com/boostorg/boost.git
  cd boost
  .\bootstrap
  .\b2 -a -j8 toolset=msvc-14.2 architecture=x86 address-model=32,64 --prefix=E:\Boost variant=debug,release link=static runtime-link=shared threading=multi install
  ```

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
  * Copy the contents of this folder to a folder called build in
    the websocketpp folder.

# Note #

To compile curl, you need 

  * [zlib, tested w/ v1.2.11](https://github.com/madler/zlib)
  * [OpenSSL, tested w/ v1.1.1e-DEV](https://github.com/openssl/openssl)
  * You can use my [openssl-x86_x64](https://github.com/sridharb1/openssl-x86_x64) to compile openssl on Windows.

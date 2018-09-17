# RADDI: *redistributable packages and libraries for Windows*

If you are using **portable** build of RADDI you can ignore this repository. All required code is already built into executable files. That's why they are so big. If you are using automatic installer, you can also ignore this.

If you are using **release** build of RADDI do following:

1. Determine appropriate platform of the raddi binaries you've downloaded or compiled
2. Download everything from that directory in this repository
3. Install msvc_redist_xxx.exe
4. Copy all .dll files into directory with your raddi executables
5. Done

## NOTE

This all will be automatically handled by installer in the future.

## OS Version Requirements

DLLs here have required subsystem version number patched to support Windows XP. Normally compiled liblzma.dll and libsodium.dll require Windows Vista.

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

## Differences from official builds

liblzma.dll and libsodium.dll available here contain following few small patches:

* **Windows XP support** - OS/subsystem version number is patched to support Windows XP for x86-32 and x86-64; regular builds of liblzma.dll and libsodium.dll require Windows Vista
* **CFG** - compiled with Control Flow Guard (security hardening) enabled
* **/PDBSTRIPPED** - unnecessary debug information removed for slightly smaller binary footprint 
* **/EMITPOGOPHASEINFO** - removes unneeded IMAGE_DEBUG_DIRECTORY from .rdata section *(undocumented option)*

## ARM-64 NOTE

There is no arm-64/sqlite3.dll. *Release* AArch64 build uses **winsqlite3.dll** (bundled with Windows 10) instead of redistributable sqlite3.dll. This means that, unlike other builds which will run on Windows XP, AArch64 build requires Windows 10 (1507 or LTSB 2015) ...which is fine, because there was no earlier public build of Windows for ARM-64 anyway.


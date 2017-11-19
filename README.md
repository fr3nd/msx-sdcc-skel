# msx-sdcc-skel

Skeleton to build MSX programs using SDCC

## Requirements

* [SDCC](http://sdcc.sourceforge.net/)
* make
* [Hex2bin](https://sourceforge.net/projects/hex2bin/) (included)
* [OpenMSX](https://openmsx.org/) (for testing)
* [OpenMSX System ROMs](http://www.msxarchive.nl/pub/msx/emulator/openMSX/systemroms.zip) (for testing)

# Usage

This repository contains a skeleton to start developing MSX programs using the SDCC cross compiler.

Example usage:
```
# Compile everything
make

# Run OpenMSX with MSX-DOS on the bin directory with the compiled programs
make test

# Delete all compiled files
make clean

# Compile all provided libs
make libs
```

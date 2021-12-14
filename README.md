# Furnace

this is a player for DefleMask module files (.dmf).

## features

- supports Sega Genesis, Master System, Game Boy, PC Engine, NES, C64, YM2151/PCM and Neo Geo!
- clean-room design (zero reverse-engineered code and zero decompilation; using official DMF specs, guesswork and ABX tests only)
- bug/quirk implementation for increased playback accuracy
- accurate emulation cores whether possible (Nuked, MAME, SameBoy, Mednafen PCE, puNES, reSID and ymfm)
- open-source. GPLv2.

## dependencies

- CMake
- SDL2
- zlib
- JACK (optional)

SDL2 and zlib are included as submodules.

## compilation

your typical CMake project. clone (including submodules) and:

### Windows using MSVC

from the developer tools command prompt:

```
mkdir build
cd build
cmake ..
msbuild ALL_BUILD.vcxproj
```

### macOS and Linux

```
mkdir build
cd build
cmake ..
make
```

## usage

```
./furnace <file>
```

this will play a .dmf file.

```
./furnace -view commands <file>
```

this will play a .dmf file and enable the commands view.

```
./furnace -loops 0 <file>
```

this will play a .dmf file and not loop it.

```
./furnace -output audio.wav <file>
```

this will render a .dmf file to .wav.

# notes

> my song plays different after looping!

that's because Furnace does not reset channel status when looping.

> my song sounds very odd at a certain point

file a bug report. use the Issues page.

it's probably another playback inaccuracy.

> extremely high CPU usage in arcade platform

yep, that's how accurate Nuked is. I'll add an ymfm-based core soon.

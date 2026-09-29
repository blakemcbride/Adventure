# Adventure (Colossal Cave)

This is Don Woods' Adventure 2.5 — the 430-point version of the classic
Colossal Cave Adventure, the original text adventure game.

## History

- Original idea and 5-treasure version by Willie Crowther
- 15-treasure version by Don Woods, April–June 1977
- 20-treasure version (Rev 2) by Don Woods, August 1978
- Version 2.5 (this one) by Don Woods, 1995 — produced by running the
  original Fortran IV source through a Fortran-to-C converter

## Modernization

The 1995 sources have been updated to compile cleanly with modern GCC
while leaving the game logic untouched:

- K&R-style function definitions converted to ANSI C prototypes with
  explicit parameter and return types (e.g. `int main(void)`,
  `void fSPEAK(long N)`)
- Standard headers (`<stdio.h>`, `<stdlib.h>`) included instead of
  relying on implicit declarations
- Time-of-day seeding uses `gettimeofday()` from `<sys/time.h>` on
  POSIX systems (the old Amiga/MS-DOS variants remain behind `#ifdef`s)

## Building

    make

This produces the `adventure` executable.

## Running

    ./adventure

The game must be run from a directory containing `adventure.text` (the
game's text database). On first run it converts `adventure.text` into a
faster-loading `adventure.data` file, which is used on subsequent runs.

## License

(c) Copyright 1995 by Donald R. Woods. This software may be freely
redistributed if the copyright notice is retained. See the LICENSE file.

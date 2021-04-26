# pix

## A proof of concept Elf/OS 1861 Pixie image display utility

A bare-bones, thrown together in a hour, Elf/OS image display utility for
[Gaston William's PicoElfPixieVideoGLCDV2](https://github.com/fourstix/PicoELfPixieVideoGLCDV2)
Teensy/1861.

It will display images in either 64x32 or 64x64 format, depending on the
file size (256 or 512 bytes respectively).

As you might expect from an hour's work, it is *delightfully* bare bones.
But as a proof of concept, it does what it's supposed to do.

There's a few images in the [images](images) subdirectory to show what
it does.

### Usage

```
   Ready
   : pix enterprise.img
   Press any key to exit...
   
   Ready
   :
```	

### Image File Format

It's as simple as it could be: a raw image dump. The bytes in the file
are displayed as-is by the code.

### Floobydust

The source was assembled with a modified version of the
[A18 assembler](https://github.com/carangil/A18) that includes *push*
and *pop* pseudo ops. The header files `bios.inc` and `kernel.inc` are
slightly modified versions of Mike Riley's files; the `#ifdef...#endif`
bits have been removed or unconditionally included as appropriate,
`#define`s changed to `equ`, and upper/lower casing was made consistent.

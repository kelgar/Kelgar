# About

> Kelgar is a beautiful world, but beneath that beauty lies darker secrets. A haunted mine, a paranoid king, an evil necromancer, a painter hiding away in a world she created for herself... you'll find all this and more in Kelgar, created with top-of-the-line indie tech! 

Kelgar is an open-world RPG, being first released in January 2013.
It is being developed by a group of passionate persons:

* **Rick (kddekadenz)** - Lead Developer
* **Torben** - Lead Environmental Artist
* **Michiel (51nt3rkl445)** - Environmental Artist
* **Paul (greenlight)** - Environmental Artist
* **Ryan (flawlesstdouble)** - Static 3D Models Creator
* **Cestmir (CDmir)** - Animated 3D Models Creator
* **Winter (Filasis Nome)** - Lead Concept Artist
* **Alan (AlanPereira)** - Concept Artist & Scripter
* **Miamelly** - Illustrator & Concept Artist
* **Thomas (cptmashek)** - Quest Designer
* **Corey (R-Y-S-E)** - Music Composer

## Engine
We're using [Lamiae](https://github.com/Hirato/lamiae) as engine, which is a fantastic octree-based first person engine being developed by Kevin 'Hirato' Meyer. It is originally based on Cube 2, thus running smooth and stable. The framework is highly flexible. Having merged the Cube 2 fork Tesseract, it also features a state of the art lighting model and other advanced rendering features, including SSAO, HDR w/ tonemapping, Radiance Hints (Global Illumination) and more.

## License
The source code of Lamiae and Kelgar is accessible under the terms of the permissive zLib License.
See LICENSE.txt for more pieces of information!
The art of Kelgar currently is excluded out of the license.

## Run Instructions
If you need to build a binary first, see the section below.


### Windows
There is a lamiae.bat in the main directory, this is your sole means of launching lamiae.
If you're having issues running the game, make sure that your drivers are properly installed and that your GPU can at least match Intel's Sandy Bridge in all aspects.


### Linux/FreeBSD
There is a script named lamiae.sh in the main directory, running this will launch the proper binary for your platform.
A multitude of command line options are available, run with --help, -h or -? to get a list.
If you have problems running it, make sure that SDL2, SDL2_mixer and SDL2_image is installed. If you have an Nvidia GPU, you should also make sure that the proprietary drivers are installed and working.


## Build Instructions

### Windows
1. Install Codeblocks ( http://www.codeblocks.org/ ) pick the no-mingw version
2. Install mingw64 with SILJ bindings ( http://tdm-gcc.tdragon.net/download )
3. Open up the codeblocks project file in src/windows/lamiae.cbp
4. Click build

* The current 32bit only tdm-gcc release (4.7.1-2) will not compile lamiae, and has other known issues.
* You may need to manually specify the paths for mingw, just point it to C:\MingW64 (or where applicable) and replace the compiler executables with their generic selves (eg mingw32-i386-unknown-gcc.exe to gcc.exe)

** Support is not provided for Visual Studio, in theory the code should compile with 2005 and later.


### Linux/FreeBSD
1. Install GCC
2. Install SDL2, sdl2_mixer and sdl2_image, as well as their *-dev counterparts
3. make -C src install

* SDL 2.0 is currently in development, and otherwise known as SDL-hg.
    Most distros don't yet package SDL 2.0, Archlinux has sdl-hg packages in the AUR with which you may use to easily build it yourself, and Ubuntu derivatives can access pre-built apckages via PPAs. You'll need to do it manually otherwise.
* if you want a debug binary instead, use "make -C src -f Makefile.debug install"
* If you're using BSD, you may need to specify the GNU version of the make utility.

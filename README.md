sdldoom-1.10-mod
================

**SDL DOOM 1.10 - modifications for linux-x64 and newer SDL**

The official SDL Doom website: http://www.libsdl.org/projects/doom/

This is a fork of the SDL port of Doom from Sam Lantinga. Since it is very old,
it doesn't work on many systems. Also there are a few bugs which need to be
fixed. The goal of this repository is to build a version which works on every
linux with every SDL and then make a few nice modifications in the game :-)  


From the Doom wiki (http://doom.wikia.com/wiki/SDL_Doom):  
> "SDL Doom or SDLDoom is an old and simple port of Doom, made by Sam Lantinga in
the year 1998. As its name states, it uses the Simple DirectMedia Library for
the drawing functions. SDL Doom is programmed in the C language and is open
source. It was the basis of the first Symbian OS Doom port, CDoom and later the
C2Doom project. It doesn't support custom WAD files. Only DOOM1.WAD, DOOM.WAD,
DOOM2.WAD, DOOMU.WAD, PLUTONIA.WAD and TNT.WAD are supported."

**Installation**

For now the game only works when SDL and the game itself are comiled in 32 bit mode. Here are some commands that will do the installation procedure for you:

Install the Linux 32-Bit librarys:

	$ sudo apt-get install ia32-libs

Download SDL 1.2 (http://www.libsdl.org/download-1.2.php), navigate into the 
downloaded SDL directory, then enter:  

	$ ./configure CFLAGS='-g -O2 -m32' LDFLAGS='-m32'  
	$ make  
	$ sudo make install

Navigate into the Doom-files directory and enter:  

	$ ./configure --disable-sdltest && sed -i s/'^CPPFLAGS ='/'CPPFLAGS = -m32'/g Makefile && sed -i s/'^LDFLAGS = '/'LDFLAGS = -m32'/g Makefile  
	$ make

Then you can start the game with:  

	$ ./doom
    
    
    
.
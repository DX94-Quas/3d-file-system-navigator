This software is provided without support and without any obligation on
the part of Silicon Graphics, Inc. to assist in its use, correction,
modification or enhancement.  There is no guarantee that this software
will be included in future software releases.  

THIS SOFTWARE IS PROVIDED "AS IS" WITH NO WARRANTIES OF ANY KIND
INCLUDING THE WARRANTIES OF DESIGN, MERCHANTIBILITY AND FITNESS FOR A
PARTICULAR PURPOSE, OR ARISING FROM A COURSE OF DEALING, USAGE OR TRADE
PRACTICE.

In no event will Silicon Graphics, Inc. be liable for any lost revenue or 
profits or other special, indirect and consequential damages, even if 
Silicon Graphics, Inc.  has been advised of the possibility of such damages.




3D File System Navigator for IRIX 4.0.1+


fsn (pronounced fusion) is a file system navigator in cyberspace.  It
lays out the directories in a hierarchy with each directory
represented by a pedestal.  The height of the pedestal is proportional
to the size of the files in the directory.  The directories are
connected by wires, on which it is possible to travel.  On top of each
directory are boxes representing individual files.  The height of the
box represents the size of the file, while the color represents the
age.

Fsn was written several years ago by myself and Steve Strasnick, as an
investigation in information landscape navigation.  It was the
progenetor of the current Tree Visualizer in the Silicon Graphics
MineSet(TM) product.  Fsn was featured in the movie Jurassic Park.

Keep in mind that fsn is a prototype and an experiment.  It is neither
a full featured product nor a replacement for a filesystem manager
such as Indigo Magic.

Fsn requires Z-buffering and RGB support.  You must be running IRIX
release 4.0.1 or greater.

There are two files available.  fsn.tar.Z should be used if you are
running IRIX 5.3, 6.2, or later.  fsn.COFF.tar.Z should be used for
earlier releases.  (fsn.tar.Z might work for prior 5.X releases, but
has not been tested.)

The file fsn.tar.Z can be uncompressed using the command:
	uncompress < fsn.tar.Z | tar xvf -
It will produce the following files:
	fsn:	The file system navigator
	fsn.z:	the compressed man page
	Fsn:	The app-defaults file
	Fsn.icon: A window manager icon
	Makefile: used to install the files

Fsn can be run as is after unpacking, or to install all of the files,
su, and run "make install".

Fsn should be invoked with a parameter specifying the top directory to
be looked at.  This directory can be "/", in which case the whole file
system is scanned.  Although the system works fine starting at "/",
startup time is somewhat longer, and movement can be chunky if you
have more than about 1500 directories.  You may prefer to start at
your home directory.  Even if you start at "/", you can still prune it
to a small size using the Prune function.  After pruning you will need
to restart fsn to reclaim the memory.

When scanning a file system, fsn will not cross file system type
boundaries.  For example, it will not cross into an NFS file system.
However, it will cross mount points of the same type of file system.

The first time fsn is run it will scan the whole file system.  Be
patient, this can take a few minutes.  After it has scanned the file
system it will save a database in your home directory so that
subsequent startups can be done in seconds rather than minutes.  On
subsequent runs the database will be read, making fsn quickly
available.

Using fsn is easy.  The manual page goes into a lot of detail, but
here is a quick overview.

The left mouse can be used to select directories and files.  Clicking
on a directory or file will select it and zoom in.

Double click with the left mouse will execute or view a file, and
"Warp" into a directory, where there is a different viewing paradigm.

The middle mouse can be used to navigate.  While holding down the
middle button, move the mouse in the direction you want to go.
The farther you move the mouse from where you clicked, the faster you go.
Shift-middle mouse also moves you up and down while moving forward and
backward.

The right mouse pops up the file menu, which can also be found on the
menu bar.

There is also an overview window (which can be hidden if you don't
want it).  This window shows you all the directories, and where you
are.  You can also use it to select (left mouse), or move (middle
mouse).

You may also want to experiment with the landscapes.  The landscapes
control the colors of sky and ground, and can be selected with the
-landscape option.  Be aware that the landscapes that use Gouraud
shading will not look all that good on an Indigo.

Your comments are appreciated.  Send any mail to joel@sgi.com.

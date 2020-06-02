.. _Wikipedia:    		https://en.wikipedia.org/wiki/POSIX

===============
MinGW Vs CygWin
===============
Before understanding the difference between MinGW and CygWin, it is essential to know about POSIX.

POSIX
=====
According to `Wikipedia`_, POSIX stands for ``Portable Operating System Interface`` and it is a family of standards specified by the IEEE Computer Society for maintaining compatibility between operating systems. POSIX defines the application programming interface (API), along with command line shells and utility interfaces, for software compatibility with variants of Unix and other operating systems. Basically it was a set of measures to ease the pain of development and usage of different flavours of UNIX by having a (mostly) common API and utilities.
When you write your programs to rely on POSIX standards, you can be pretty sure to be able to port them easily among a large family of Unix derivatives (including Linux, but not limited to it!); POSIX is a good thing to have as such it eases the software development for maximum portability which it strives for.
Mac OSX is Unix-based (and has been certified as such), and in accordance with this is POSIX compliant. POSIX guarantees that certain system calls will be available. Essentially, Mac satisfies the API required to be POSIX compliant, which makes it a POSIX OS.
All versions of Linux are not POSIX-compliant. Kernel versions prior to 2.6 were not compliant, and today Linux isn't officially POSIX-compliant because they haven't gone out of their way to get certified (which will likely never happen). Regardless, Linux can be treated as a POSIX system for almost all intents and purposes. Linux adheres to the spec, but hasn't certified yet

CygWin
======
Cygwin provides a POSIX compliant Unix-like environment to allow programs of Unix-like systems to be recompiled and run natively on Windows with minimal source code modifications by providing them with the same underlying POSIX API they would expect in those systems. Cygwin consists of two parts: ``cygwin1.dll`` a dynamic-link library (DLL) that serves as a Linux emulator providing a substantial part of the POSIX API functionality, and the tool set provides the Linux-like development environment. This capability helps developers to migrate applications from Unix or Linux to Windows-based systems, and makes it easier to support their applications running on the Windows platform. The name Cygwin was created from a combination of Cygnus and Windows.

Cygwin does not provide a means for directly running GNU/Linux or other Unix binary executables under MS-Windows. In order to run such software using Cygwin, that software must be compiled from its sources. Cygwin provides all of the components needed to do this in most cases; most POSIX-compliant software, including X11 applications, can easily be ported to MS-Windows using Cygwin.

In a nutshell, Cygwin is a combination of POSIX compatibility layer (encapsulated in cygwin1.dll) on top of windows API and a set of open source tool compiled with this dll to ease the recompilation of linux tools from source code to be able to run it on windows.

The purpose of Cygwin is to make porting Unix-based applications to Windows much easier, by emulating many of the small details that Unix-based operating systems provide, and are documented by the POSIX standards.
When you distribute your software, the recipient will need to run it along with the Cygwin run-time environment (provided by the file cygwin1.dll). which will act as a compatibility layer around your application, so that many of those Unix-specific paradigms can continue to be used.

.. note::

	The main reason why we have a POSIX emulation layer is that many of the common POSIX compilant function calls such as fork, which are available in \*nix variants, are not available in Windows.

.. warning::

	Cygwin and Mingw are not always interchangeable alternatives.

MinGW
=====
MinGW aims to simply be a Windows port of the GNU compiler tools, such as GCC, Make, Bash, and so on. It does not attempt to emulate or provide comprehensive compatibility with Unix, but instead it provides the minimum necessary environment to use GCC (the GNU compiler) and a small number of other tools on Windows. It does not have a Unix emulation layer like Cygwin, but as a result your application needs to specifically be programmed to be able to run in Windows, which may mean significant alteration if it was created to rely on being run in a standard Unix environment and uses Unix-specific features such as those mentioned earlier. By default, code compiled in MinGW's GCC will compile to a native Windows X86 target, including .exe and .dll files, though you could also cross-compile with the right settings, since you are basically using the GNU compiler tools suite.

MinGW is essentially an alternative to the Microsoft Visual C++ compiler and its associated linking/make tools. It may be possible in some cases to use MinGW to compile something that was intended for compiling with Microsoft Visual C++, with the right libraries and in some cases with other modifications.



    MinGW forked from version 1.3.3 of Cygwin. Although both Cygwin and MinGW can be used to port UNIX software to Windows, they have different approaches: Cygwin aims to provide a complete POSIX layer that provides emulations of several system calls and libraries that exist on Linux, UNIX, and the BSD variants. The POSIX layer runs on top of Windows, sacrificing performance where necessary for compatibility. Accordingly, this approach requires Windows programs written with Cygwin to run on top of a copylefted compatibility library that must be distributed with the program, along with the program's source code. MinGW aims to provide native functionality and performance via direct Windows API calls. Unlike Cygwin, MinGW does not require a compatibility layer DLL and thus programs do not need to be distributed with source code.

    Because MinGW is dependent upon Windows API calls, it cannot provide a full POSIX API; it is unable to compile some UNIX applications that can be compiled with Cygwin. Specifically, this applies to applications that require POSIX functionality like fork(), mmap() or ioctl() and those that expect to be run in a POSIX environment. Applications written using a cross-platform library that has itself been ported to MinGW, such as SDL, wxWidgets, Qt, or GTK+, will usually compile as easily in MinGW as they would in Cygwin.

    The combination of MinGW and MSYS provides a small, self-contained environment that can be loaded onto removable media without leaving entries in the registry or files on the computer. Cygwin Portable provides a similar feature. By providing more functionality, Cygwin becomes more complicated to install and maintain.

    It is also possible to cross-compile Windows applications with MinGW-GCC under POSIX systems. This means that developers do not need a Windows installation with MSYS to compile software that will run on Windows without Cygwin.


References
==========
https://unix.stackexchange.com/questions/11983/what-exactly-is-posix
https://stackoverflow.com/questions/1780599/what-is-the-meaning-of-posix
http://cygwin.org/
https://stackoverflow.com/questions/22707447/what-is-cygwin-and-what-does-it-do
https://stackoverflow.com/questions/771756/what-is-the-difference-between-cygwin-and-mingw/771774#771774
http://www.mingw.org/wiki/MinGW
https://en.wikipedia.org/wiki/MinGW#Comparison_with_Cygwin
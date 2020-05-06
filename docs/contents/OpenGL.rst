.. |copy|   unicode:: U+000A9 .. COPYRIGHT SIGN

==========================
OpenGL
==========================
OpenGL is a platform independent specification for rendering a 3D scene on a 2D screen. The specifications have been constantly developed by a consortium of GPU manufactures.
	
The history of OpenGL is succinctly given in https://glumpy.github.io/modern-gl.html
	
.. figure:: https://glumpy.github.io/_images/gl-history.png
    :align: center
    :alt: alternate text
    :figclass: align-center

    History of OpenGL Copyright |copy| `glumpy <https://glumpy.github.io/modern-gl.html>`_

OpenGL in Windows
=================
The default Windows installation does not ship with fully featured OpenGL drivers. It provides just OpenGL 1.1 out of the box using opengl32.dll.  It's a software-emulated version of OpenGL 1.1. The old 1.1 implementation is a software emulation of that what the GPU does. When you call the opengl32.dll to initialize, it checks if there is an alternative version of gl and load that into the execution space of opengl32.dll, otherwise fallback to the build in functionality. The OpenGL driver model allows your hardware vendor to install another DLL somewhere on your OS. The name and location of this DLL are both vendor-specific, and may change between different driver revisions. The opengl32.dll detects if this is present (by reading a registry key) and re-routing all OpenGL calls to it.

So you're not actually calling directly into the opengl32.dll at all. The opengl32.dll is taking your OpenGL calls, checking if the vendor's DLL is present, and calling into the vendor's DLL for you. That's where hardware acceleration comes from.

OpenGL comes with windows. Just include <GL/glu.h> to use utility functions starting with glu and include <> for general OpenGL function. Also include the libraries LIBS += -lopengl32 -lglu32

Software emulation mode & Hardware Accelerated Mode


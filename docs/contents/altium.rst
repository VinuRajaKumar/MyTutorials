=========================
Altium
=========================


+-----------+----------------------------------+
| Extension | File                             |
+-----------+----------------------------------+
| \*.DsnWrk | Design Workspace                 |
+-----------+----------------------------------+
| \*.PrjPcb | PCB Project File                 |
+-----------+----------------------------------+
| \*.SchDot | Project Template File            |
+-----------+----------------------------------+
| \*.SchDoc | Schematic Sheet File             |
+-----------+----------------------------------+
| \*.SchLib | Schematic Component Library File |
+-----------+----------------------------------+

-----------
Preferences
-----------
	Project settings and preferences can be accesed from ``Tools->Preferences``
	

Access Document Templates
-------------------------

	``Data Management->Templates->Template Location``
					
Set **Project Defaults**
------------------------
	``System->Default Locations``

The following options can be set,
Document Path : Specifies the default directory which appears in "Project Path" when File->New Project is selected.

Library Path : Location of default library path

Set **New Document Defaults**
-----------------------------
	``System->New Document Defaults``

Specifies the default document files for different file types

Install **Schematic (*.SchLib) Libraries**
------------------------------------------
	``Data management->File-based Libraries``

Show/Hide the pin direction
---------------------------			
	``Schematic-General->Pin Direction``

Drag wire along with the component 
----------------------------------
	``Schematic-Graphical Editing->Always drag``

Show negation in single '\'
---------------------------
	``Schematic-Graphical Editing->Single '\' Negation``

Remove junction dots
--------------------
	``Schematic-Compiler->Auto-Junctions->Disply On Wires``

Set "snap to grid" points
-------------------------			
	``Options->Document Options->Library Editor Options->Grids``
			
3D view Navigation
------------------
	``Shift + RightMouse Button``

Reorient rotated Strings
------------------------
	``references->Schematic->Graphical Editing->uncheck (or maybe check) the box for Display Strings as rotated.`` 

Altium
	Show 3D Bodies : CNTL+Z

Orthographic & Perspective Projection
	Right side Bottom Panel -> View Configuration
	
Single Layer Mode
	SHIFT+S

Zero Rotation	0
90 Deg Rotation 9
Orthogonal Rotation 8

Clear the selection of the Find Similar Objects
-----------------------------------------------           
	
After performing the edit, you will probably find that all the other objects on the schematic are faded out, or masked. While something is masked it cannot be edited, to remove the mask click the Clear button at the bottom right of the workspace [shortcut: SHIFT + C]

Change the generated pdf background color
-----------------------------------------
	Open the Template file and change the background color.
	
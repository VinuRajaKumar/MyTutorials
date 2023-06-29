MiKTeX packages offline installation (Windows)
==============================================
1. Go to `CTAN Comprehensive TeX Archive Network <https://ctan.org/pkg/>`_

2. Search the required package and download.

Example : `appendix.zip <http://mirrors.ctan.org/macros/latex/contrib/appendix.zip>`_

It contains a minimum of two files; `dtx` is the extension of a documented source file, `ins` is the extension of an installation file.

3. Extract the file into a local directory(appendix).

4. Open a command prompt, Navigate to the extracted directory and run the following commands

 .. code-block:: bash
 
	latex appendix.ins
	latex appendix.dtx
	makeindex -s gind.ist appendix
	latex appendix.dtx
	
The first command generates appendix.sty

5. Create a folder "localtexmf" on your computer

	Example : c:/localtexmf)

6. Create a TDS compliant directory structure. i.e. atleast a tex/latex subtree should be sufficient.

	Example : c:/localtexmf/tex/latex
	
7. Copy the directory appendix along with its contents to c:/localtexmf/tex/latex

	Example : c:/localtexmf/tex/latex/appendix/*
	
8. Run the following commands in a command windows

 .. code-block:: bash
 
	initexmf --admin --register-root=c:\localtexmf
	initexmf --admin --update-fndb
	
[OR]
				
	a. Open MiKTeX Console.
	
	b. Select "Switch to MiKTeX administrator mode" under operational mode
	
	c. Once it enters to MiKTex Console (Admin), Select "Directories" Tab under Settings.
	
	d. Add the path "c:/localtexmf"
	
	e. Select Refresh file name database (FNDB)" under tools.
	
9. Now the package is ready for usage in LaTex document.

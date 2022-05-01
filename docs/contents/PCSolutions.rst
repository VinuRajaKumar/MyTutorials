============================
PC Common Issues & Solutions
============================

1. Enable "Insert" in context menu
##################################

		a) Press Alt+F11
		b) Double Click on a Worksheet
		c) Paste the below code and press F5.
		
 .. code-block:: basic
 
		Sub reset()
			On Error Resume Next
			For Each c In Application.CommandBars
				c.reset
			Next
		End Sub

(OR)

 .. code-block:: basic
 
		Public Sub MenuReset()
			CommandBars("column").Reset
			CommandBars("row").Reset
			CommandBars("Cell").Reset
		End Sub

2. Disable "Insecure Password Warning" on Firefox
#################################################

		a) Open a new Tab, type about:config in the address bar and Hit Enter
		b) If you see the "This might Void Your Warranty" page, Click the blue "I accept the risk!" button.
		c) Search for insecure_field_warning.contextual.enabled
		d) Double click the setting to change it to "false"

3. Disable Firfox's nagging update message.
###########################################

a) Create a file policies.json with the following contents.
		
 .. code-block:: json
 
		{
			"policies": {
			"DisableAppUpdate": true
			}
		}

b) Create a folder named "distribution" and place the "policies.json" inside it.
c) Place the "distribution" folder where the firefox executable is located. Normally, "C:\Program Files\Mozilla Firefox" in windows

4. Show Hidden files in pendrive
################################
		a) Type cmd in search box of start menu in Windows 7 or Type cmd in the run box of Windows XP
		b) Find the removable drive letter identification in "My Computer". [Example  "H:"]
		c) Type the drive letter with a colon in the command window and press Enter. [Example H:]
		d) Now command window should change to the drive letter. [Example H:/]
		e) Type attrib -r -h -s *.* /S /D and then press Enter. Notice the spaces in between.
		f) Grab a cup of tea, it may take sometime depending on the number of Files/Folders.
		g) Once command execution is over, all your files and directories become visible.
		h) Type help attrib in a command prompt for an explanation of the command.

5. Windows: Ignore errors with Xcopy and RoboCopy
#################################################

Posted on December 1, 2010 by Randy	

To copy entire directory structures as quickly as possible and ignore all disk errors (useful in data recovery) either of the following commands should work with robocopy being the quickest (if you’ve got Vista/7 or XP with the XP Resource Kit installed). Both commands use source -> destination path order.

xcopy /C/H/R/S/Y c:\ d:\

/C = Continues copying even if errors occur
/H = Copies hidden and system files also
/R = Overwrites read-only files
/S = Copies directories and subdirectories
/Y = Overwrites existing files without asking

robocopy c:\ d:\ /MIR /R:0 /W:0

/MIR = Mirror entire directory structure (can use /E instead)
/R:0 = 0 retries for read/write failures
/W:0 = 0 seconds between retries


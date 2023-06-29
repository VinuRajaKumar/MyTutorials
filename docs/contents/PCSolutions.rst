============================
PC Common Issues & Solutions
============================

1. [Microsoft Excel] Enable "Insert" in context menu
####################################################

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

2. [Mozilla Firefox] Disable "Insecure Password Warning"
########################################################

a) Open a new Tab, type about:config in the address bar and Hit Enter
b) If you see the "This might Void Your Warranty" page, Click the blue "I accept the risk!" button.
c) Search for insecure_field_warning.contextual.enabled
d) Double click the setting to change it to "false"

3. [Mozilla Firefox] Disable nagging update message
###################################################

a) Create a file policies.json with the following contents.
		
 .. code-block:: json
 
		{
			"policies": {
			"DisableAppUpdate": true
			}
		}

b) Create a folder named "distribution" and place the "policies.json" inside it.
c) Place the "distribution" folder where the firefox executable is located. Normally, "C:\Program Files\Mozilla Firefox" in windows

4. [Microsoft Windows XP/7/8/10/11] Show Hidden files in pendrive
#################################################################
a) Type cmd in search box of start menu in Windows 7 or Type cmd in the run box of Windows XP
b) Find the removable drive letter identification in "My Computer". [Example  "H:"]
c) Type the drive letter with a colon in the command window and press Enter. [Example H:]
d) Now command window should change to the drive letter. [Example H:/]
e) Type attrib -r -h -s *.* /S /D and then press Enter. Notice the spaces in between.
f) Grab a cup of tea, it may take sometime depending on the number of Files/Folders.
g) Once command execution is over, all your files and directories become visible.
h) Type help attrib in a command prompt for an explanation of the command.

5. [Microsoft Windows 10/11] Set Windows+E key to open “This PC”/"My Computer" instead of Quick Access
######################################################################################################
a) Open "Folder Options" dialog.
	i) Press "WIN" + "E" to open File Explorer.
	ii) Click the View tab.
	iii) Click Options in the ribbon

OR

	i) Press "WIN" + "R" keys to open the Run command box.
	ii) Type ``control.exe folders`` and press Enter

b) Select "This PC" next to "Open File Explorer to"

6. [Microsoft Windows 10/11] Restart windows computer in safe/recovery mode
###########################################################################
a) Open Command Prompt.
b) Type the following command and press Enter

 .. code-block:: bash

	shutdown /f /r /o /t 0

7. [Microsoft Windows 10/11] Remove an update with Command Prompt
#################################################################
a) Open Command Prompt.

b) List installed windows updates

 .. code-block:: bash

	wmic qfe list brief /format:table

b) Uninstall the HotFixID

 .. code-block:: bash
 
	wusa /uninstall /kb:HotFixID

8. Windows: Ignore errors with Xcopy and RoboCopy
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


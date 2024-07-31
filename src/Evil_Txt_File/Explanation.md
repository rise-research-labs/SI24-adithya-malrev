### Technical Details
- CVE-2024-30050
- Windows Mark of the Web Security Feature Bypass Vulnerability

### About the Exploit
- This is a UAC bypass technique that abuses `.URL` and `.LNK` files.

### What is a URL file?
- It is an Internet Explorer era file that acts as a shortcut file.
- It is designed to link to websites, but it can be used to reference files.
- In this exploit it is used to call a local executable from a remote machine.

### URL working directory bypass
- Referencing a remote file using a `.url` file will prompt a warning message.
- Referencing a local file will not prompt a warning message.
- The `WorkingDirectory` parameter allows us to define the directory in which the executable is executed. This can be either local or remote.
- In this exploit a local executable is referenced from a remote server without triggering the warning message.
- The `WorkingDirectory` for this executable is a folder on the remote server. The executables that search for specific files within the directory will now use the files from the remote server instead.

### stordiag.exe
- Storage Diagnostic Tool allows System Administrators to collect and analyze storage-related data, which can help them troubleshoot Hard Disk and storage diagnostic issues. It can collect all storage and file system-related data and diagnostic logs and output them to a folder.
- stordiag.exe is designed to search the working directory for a file named as `powershell.exe`.
- This exploit uses a `.url` shortcut file to call `stordiage.exe` and then run it within a remote file share with a malicious executable named as `powershell.exe`.

### .LNK files and Archives
- `.lnk` is a shortcut file.
- It can be used to run files from within the archive. It will give a user prompt unless the file being referenced is a trusted file type.
- `.url` is a trusted file type. So it does not prompt the user when referenced by the `.lnk` file.




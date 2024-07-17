GitHub repo with UAC bypass techniques.
https://github.com/hfiref0x/UACME

Tested on Windows 11 Pro N 23H2 
OS Build - 22631.3737

### 1. Exploit 33
	Author: winscripting.blog
	Type: Shell API
	Method: Registry key manipulation
	Target(s): \system32\fodhelper.exe
	Component(s): Attacker defined
	Implementation: ucmShellRegModMethod
	Works from: Windows 10 TH1 (10240)
### 2. Exploit 53
	Author: Emeric Nasi
	Type: Shell API
	Method: Registry key manipulation
	Target(s): \system32\sdclt.exe
	Component(s): Attacker defined
	Implementation: ucmShellRegModMethod
	Works from: Windows 10 (14393)

### 3. Exploit 61
	Author: Enigma0x3/bytecode77 derivative by Nassim Asrir
	Type: Shell API
	Method: Registry key manipulation
	Target(s): \system32\slui.exe, \system32\changepk.exe
	Component(s): Attacker defined
	Implementation: ucmShellRegModMethod
	Works from: Windows 10 (14393)

### 4. Exploit 62
	Author: winscripting.blog
	Type: Shell API
	Method: Registry key manipulation
	Target(s): \system32\computerdefaults.exe
	Component(s): Attacker defined
	Implementation: ucmShellRegModMethod
	Works from: Windows 10 RS4 (17134)

### 5. Exploit 70
	Author: V3ded 
	Type: Shell API
	Method: Registry key manipulation
	Target(s): \system32\fodhelper.exe, \system32\computerdefaults.exe
	Component(s): Attacker defined
	Implementation: ucmShellRegModMethod
	Works from: Windows 10 (10240)

The registry key exploits work by modifying the values of the registry keys accessed during the execution of programs with administrative privileges.
### 6. Exploit 41
	Author: Oddvar Moe
	Type: Elevated COM interface
	Method: ICMLuaUtil
	Target(s): Attacker defined
	Component(s): Attacker defined
	Implementation: ucmCMLuaUtilShellExecMethod
	Works from: Windows 7 (7600)
ICMLuaUtil interface exploit (part of the UAC mechanism).
### 7. Exploit 43
	Author: Oddvar Moe derivative
	Type: Elevated COM interface
	Method: IColorDataProxy, ICMLuaUtil
	Target(s): Attacker defined
	Component(s): Attacker defined
	Implementation: ucmDccwCOMMethod
	Works from: Windows 7 (7600)
Display Color Calibration Wizard exploit.

### 8. Exploit 59
	Author: James Forshaw
	Type: AppInfo ALPC
	Method: RAiLaunchAdminProcess and DebugObject
	Target(s): Attacker defined
	Component(s): Attacker defined
	Implementation: ucmDebugObjectMethod
	Works from: Windows 7 (7600)
AppInfo ALPC (Advanced Local Procedure Call) service exploit.

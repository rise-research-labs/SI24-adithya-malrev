https://github.com/Offensive-Panda/.NET_PROFILER_DLL_LOADING/

.NET profiler DLL loading can be abused to make a legit .NET application load a malicious DLL using environment variables.

Three environment variables need to be set:
1. COR_ENABLE_PROFILING=1 (Enable profiling)
2. COR_PROFILER={A2D4B6C7-1234-5678-9ABC-DEF012345678} (GUID of the DLL)
3. COR_PROFILER_PATH=`C:\Users\Public\led.dll` (Path to the DLL)

If a .NET application is run, it loads the DLL from the path specified with admin privileges without triggering UAC.

# Usage

1. Place compiled DLL (led.dll) in `C:\Users\Public` folder.
2. Build project using Visual Studio and execute compiled binary.
3. You will get admin shell, DLL is executing command to open cmd.exe.
4. Tested on Windows 10 Pro N 21H2 Build 19044.1288



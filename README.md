# SniperPOV

By default, in a POV demo, TF2 makes the local sniper invisible when you scope in. This is a small loader that fixes that.
Meant to be used alongside HLAE.

# Instructions 

Method 1 (HLAE only): Open HLAE's custom loader and add this SniperPOV.dll to the list of dlls, then press OK to launch.
Method 2 (HLAE & Lawena): You need a special version of Lawena, which can be obtained here: https://github.com/wgez/lawena-recording-tool/releases.
Method 3 (RISKY - HLAE & Injector): If you have an injector file and know what you're doing, you can inject SniperPOV.dll after launching HLAE. Heed the warning below.

## DO NOT RUN WITHOUT INSECURE MODE

If you want to inject this without HLAE, DO NOT FORGET TO USE INSECURE MODE. You WILL be VAC banned if you forget and accidentally join a VAC protected server.

## Updates

The stability of this tool is vulnerable to TF2 updates, so if it breaks please make an issue.

## How to Build (for developers)
1. Install GIT bash (to obtain source code) - https://git-scm.com/downloads
2. Install Visual Studio (not Visual Studio Code) with "Desktop development with C++" - https://visualstudio.microsoft.com/
3. From within Visual Studio, obtain the source code from this repository into a folder you like (Clone a Repository option, upon startup).
4. In a separate instance (can restart VS), obtain the source code for Microsoft Detours (https://github.com/microsoft/Detours).
4a. Build Detours for x86 (Build -> Build Solution). It will generate a "detours.lib" file at "[your repos location]/Detours/lib.X86/".
5. Reopen the SniperPOV project (with SniperPOV.sln).
6. Open the Configuration Manager (Build -> Configuration Manager...).
6a. Change "Active solution configuration" to "Release" and "Active solution platform" to "x86.
6b. Confirm below that "Configuration" is set to "Release" and "Platform" is set to "Win32". 
7. Go to Project -> Properties -> Linker -> Additional Library Directories: add the directorry that contains detours.lib.
8. Build -> Build Solution. This will generate a SniperPOV.dll file at "[your repos location]/SniperPOV/SniperPOV/Release" (note: there is no injector file supplied by this code).
Note: These are the assumed steps. Notify if it needs to be amended.

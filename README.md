# How to using this class?

```cs

ApplicationLoader.PROCESS_INFORMATION processInfo = new ApplicationLoader.PROCESS_INFORMATION();

bool processResult = ApplicationLoader.StartProcessWithAdministrator
(
    applicationName: $@"cmd.exe", 
    windowHidden: true,
    procInfo: out procInfo
);

if(processResult)
{
  //Process is started. & Created new process.
  //Created process id: (int)processInfo.dwProcessId

  //Get Process detail;
  Process process = Process.GetProcessById((int)processInfo.dwProcessId);
}
else
{
  //Process start is failed. & Don't create a new process!.
}

```


# What is the *ApplicationLoader.PROCESS_INFORMATION* ?
**ApplicationLoader.PROCESS_INFORMATION**, It contains information about the created process. It contains information such as Process Id (PID) and Thread Id.

# What is the *ApplicationLoader.StartProcessWithAdministrator* ?
This function runs the application in the given file location under 'NT AUTHORITY\SYSTEM' using system rights.
Function parameters;
1.  Application path.
2.  Windows Hidden status. (Default is false)
3.  The desired PROCESS_INFORMATION struct object to hold running process information. 
4. **Returns:** If the process runs successfully, it returns **True**. If the process could not be started, it returns **False**.

using the function;
```cs

bool processResult = ApplicationLoader.StartProcessWithAdministrator
(
    applicationName: $@"cmd.exe", 
    windowHidden: true,
    procInfo: out PROCESS_INFORMATION_Struct_Is_Here
);

````


# Photos

![ApplicationLoadPhoto](https://github.com/MevlutCanTuraci/Win-Service-Start-Process-Helper/assets/53406778/a5fea601-82c4-4bb9-bc5d-d0bc6fd0bfb1)














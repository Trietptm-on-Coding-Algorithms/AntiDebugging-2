# anti-debug
Anti-debugger and anti-reverse engineering techniques

----

- **IsDebuggerPresent**

Using the Windows API function *IsDebuggerPresent* you can determine if your process is being debugged. This function works by checking the processes PEB structure's BeingDebugged value, located at 0x2. If this PEB value is set to 1, the process is being debugged, and 0 means it's not.

- **GetProcessMemoryInfo**

Using the Windows API function *GetProcessMemoryInfo* you can determine if your process is being debugged. This function can check the working set, which is the amount of memory a process needs at a certain time. Non-debugged processes never require a great amount, you can use this idea with a simple check to see if the working set is a huge amount or not.

- **FindWindow**

Using the *FindWindow* function, you can detect specific debuggers based on window classes, you can manually provide specific window class strings that match to potential debuggers on the system, if this function finds them, it can detect it's being debugged.

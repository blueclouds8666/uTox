# Troubleshooting and common problems

If you are having troubles while trying to compile our software, here are some common problems we've discovered and instructions on how to fix them.
<br />
<br />

## CMake generate errors

Different system configurations may cause CMake to fail. Here are some things you can try:

**A. Modify the system PATH variable to defaults.**
The PATH system variable might have been changed by other applications such as GIT or Cygwin. This causes CMake to not find the proper MinGW components. Global variables may be changed at:
Start menu > right click on My PC > Properties > Advanced > Environment Variables...
On "System variables", check the "Path" variable. You can modify it but since it completely deppends on each context, we can't provide a global solution to that. 
We recommend changing it to its default value:
> %SystemRoot%\system32;%SystemRoot%;%SystemRoot%\System32\Wbem

**B. Manually specify MinGW component paths.**
Sometimes CMake might have trouble finding your MinGW components. We can manually specify them by:
1. On the CMake window, click on Add Entry. Enter this values:

> - *Name:* CMAKE_C_COMPILER
> - *Type:* FILEPATH
> - *Value:* C:/MinGW/bin/i686-w64-mingw32-gcc.exe

2. Click OK. We will need to add another value:

> - *Name:* CMAKE_MAKE_PROGRAM
> - *Type:* FILEPATH
> - *Value:* C:/MinGW/bin/mingw32-make.exe

3. finally, add this one:

> - *Name:* CMAKE_SH
> - *Type:* FILEPATH
> - *Value:* C:/MinGW/msys/1.0/bin/sh.exe


## Still no luck?

You've tried it all but you are still having problems compiling μTox? We suggest the following:

**A. Check the compiling video guide.**
Maybe you are doing some compiling steps the wrong way or you couldn't understand it well.
We've made a video guide that shows step-by-step how we managed to compile μTox. 
It might be helpful on these cases, so please check it out in here.

**B. Try the process on a isolated virtual machine.**
It commonly happens that certain system configuration and software cause conflicts with the compiling process.
We highly encourage you to try the compiling process under a VM, since it sets up a perfect enviroment and has been tested with our process.
These are some popular virtualization programs we recommend:

- Parallels Desktop for Mac. Parallels International GmbH. (Paid software). [Homepage](https://www.parallels.com/products/desktop/)
- Oracle VM VirtualBox. Oracle Corporation. (FOSS software). [Homepage](https://www.virtualbox.org)
 
There are tons of guides on how to set up a VM on the internet if you need to check them.
Best option is to clean install Windows XP SP3 (32-bits), with 1GB of system memory.

**C. Ask on the issues tab.**
As a last resort, you can always ask our community and we can try to help you.
Remember that you will need to have a github account in order to post on the issues panel.



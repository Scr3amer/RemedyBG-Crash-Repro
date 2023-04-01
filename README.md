# RemedyBG-Crash-Repro
Found a crash repro for RemedyBG  v0.3.8.7

To repro it you need the dynamic accurate monitor name fetching feature of GLFW. It is still in review but you can get it here:  
https://github.com/Scr3amer/glfw/tree/Dynamic-accurate-monitor-name-fetching

I use this toolchain: Clang 16 + MinGW + UCRT, I don't know if the bug would happen with any other toolchain:  
https://github.com/mstorsjo/llvm-mingw/releases/tag/20230320

I put a cmake with my build config.

### IMPORTANT NOTE:  
You need to build both GLFW and this with **PDB support**. I enabled it here but not in the GLFW repo.  
You need to add **-g -gcodeview as a compiler flag**  
You need to add **-Wl,--pdb= as a linker flag**

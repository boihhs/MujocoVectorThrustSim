# A copy of the GLFW library is required to build some sample programs.
# If this is not already installed on your system, download the WIN64 archive
# from https://github.com/glfw/glfw/releases, and copy files as follows:
# - Copy the entire `include/GLFW` subdirectory to `mujoco/include/GLFW`.
# - Copy glfw3dll.lib from the subdirectory corresponding into your compiler
#   choice to `mujoco/lib/glfw3dll.lib`.
# - Copy glfw3.dll from the same subdirectory into `mujoco/bin/glfw3.dll`.

COMMON=/O2 /MT /EHsc /arch:AVX /I../include /Fe../bin/

all:
	cl $(COMMON) testxml.cc                                ../lib/mujoco.lib
	cl $(COMMON) testspeed.cc                              ../lib/mujoco.lib
	cl $(COMMON) compile.cc                                ../lib/mujoco.lib
	cl $(COMMON) derivative.cc /openmp                     ../lib/mujoco.lib
	cl $(COMMON) basic.cc              ../lib/glfw3dll.lib ../lib/mujoco.lib
	cl $(COMMON) record.cc             ../lib/glfw3dll.lib ../lib/mujoco.lib
	cl $(COMMON) simulate.cc uitools.c ../lib/glfw3dll.lib ../lib/mujoco.lib
	del *.obj

These are MagLua scripts to run ompi simulations of FCC array of maghemite nanoparticles.
MagLua is a scripting language developed by Jason Mercer based on Lua language as a scripting interface with subroutines written in C/C++.
MagLua can be found at https://github.com/jasonimercer/maglua
The file "maglua.html" contains more information about MagLua and the documentation of its Revision-307.
The scripts here require MagLua r-307 https://github.com/jasonimercer/maglua/releases/tag/r307
The file "MKT.lua" will generate the matrices ("8x8x8_fcc.lua") used to calculate  the energy and and the effective fields for an 8x8x8 FCC lattice of point dipoles with periodic boundary conditions.
"A.lua" is the main file where the dipole Macro array is built and the dipole fields is calculated.
"DenseSphere.lua" contains the scripts to build sLLG objects and functions for the nanoparticles.
"SetupSphericalParticle.lua" contain the function to build the nanoparticle crystal and its exchange and anisotropy.
Excuting initial Job with defaul equilibration time can be done similar to: mpirun -np 512 maglua A.lua
Excuting from a saved point can be done in the form: mpirun -np 512 maglua A.lua load $T again $t final
Where "load $T" is to load from a saved point at temperature $T. Add "again $t" to extend equilibration to the value $t (in time unites).
Add final in case the saved point was the last saved equilibration point saved at $T (the files have names like "SSS$T.f.$rank.dat")




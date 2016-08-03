<<<<<<< HEAD
These are MagLua scripts to run ompi simulations of FCC array of maghemite nanoparticles.
MagLua is a scripting language developed by Jason Mercer based on Lua language as a scripting interface with subroutines written in C/C++.
MagLua can be found at https://github.com/jasonimercer/maglua
The file "maglua.html" contains more information about MagLua and the documentation of its Revision-307.
The scripts here require MagLua r-307 https://github.com/jasonimercer/maglua/releases/tag/r307
MagLua r-307 was built using Lua 5.1.5 which is available at https://www.lua.org/ftp/lua-5.1.5.tar.gz 

The file "MKT.lua" will generate the matrices ("8x8x8_fcc.lua") used to calculate  the energy and and the effective fields for an 8x8x8 FCC lattice of point dipoles with periodic boundary conditions.
"A.lua" is the main file where the dipole Macro array is built and the dipole fields is calculated.
The dipole Macro array is the periodic 8x8x8 FCC dipole array with each dipole have the magnetic moment of one of the nanoparitcles. it is created just to calculate the dipole field.
"DenseSphere.lua" contains the scripts to build sLLG objects and functions for the nanoparticles.
"DenseSphere.lua" is used in the initial run (no saved point to load from).
"DenseSphereL.lua" is similar to  "DenseSphere.lua" but it used when the system is loaded from saved point.
"SetupSphericalParticle.lua" contain the function to build the nanoparticle crystal and its exchange and anisotropy.
Excuting initial Job with defaul equilibration time can be done similar to: mpirun -np 512 maglua A.lua
Excuting from a saved point can be done in the form: mpirun -np 512 maglua A.lua load $T again $t final
Where "load $T" is to load from a saved point at temperature $T. Add "again $t" to extend equilibration to the value $t (in time unites).
Add final in case the saved point was the last saved equilibration point saved at $T (the files have names like "SSS$T.f.$rank.dat")
=======
The file "MKT.lua" will generate the tensors of dipole interactions (8x8x8_fcc.lua)
"A.lua" is the main file
These scripts require MagLua r-307 https://github.com/jasonimercer/maglua/tree/r307
Excuting jobs is in the form:

mpirun -np 512 maglua A.lua load $T again $t final

# load $T to load SSS$T.rank.dat, again $t to extend relaxation at T till time=$t, add "final" option to load SSS$T.f.rank.dat
# arguments places should be as mentioned
# to run defaults command is only:
#mpirun -np 512 maglua A.lua
>>>>>>> 6a60c7f21241ecde9ca3ec900d0a1ada2aa48fdc




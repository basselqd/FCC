The file "MKT.lua" will generate the tensors of dipole interactions (8x8x8_fcc.lua)
"A.lua" is the main file
These scripts require MagLua r-307 https://github.com/jasonimercer/maglua/tree/r307
Excuting jobs is in the form:

mpirun -np 512 maglua A.lua load $T again $t final

# load $T to load SSS$T.rank.dat, again $t to extend relaxation at T till time=$t, add "final" option to load SSS$T.f.rank.dat
# arguments places should be as mentioned
# to run defaults command is only:
#mpirun -np 512 maglua A.lua




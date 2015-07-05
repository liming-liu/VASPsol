Implicit solvation model for VASP
==================================

**Authors:** Kiran Mathew and Richard Hennig

http://vaspsol.mse.ufl.edu/

**For discussions and feedback:**

 https://groups.google.com/forum/#!forum/vaspsol

**References:**

If you use the VASPsol package in your research, please cite the following paper:

Implicit solvation model for density-functional study of nanocrystal surfaces and reaction pathways.
 K. Mathew, R. Sundararaman, K. Letchworth-Weaver, T. A. Arias, and R. G. Hennig. J. Chem. Phys. 140, 084106 (2014), [doi:10.1063/1.4865107] (http://dx.doi.org/10.1063/1.4865107).

PREREQUISITES
=============
[VASP](http://www.vasp.at/) versions 5.2.12 or 5.3.3 or 5.3.5 or 5.4.1.

Compiler and library requirements are the same as that of VASP ([vasp wiki] (http://cms.mpi.univie.ac.at/wiki/index.php/Installing_VASP))

INSTALL
========

**For VASP versions >= 5.4.1:**

These versions of VASP come with hooks for running solvation calculations.
The only thing required is to copy the solvation.F file to the src/ folder in the original VASP folder and 
follow the install instructions for the original VASP.

**For VASP versions = 5.2.12 or 5.3.3 or 5.3.5:**

- Apply the appropriate interface patch to the original VASP source code. There are 3 interface_patch files 
available, one for each supported versions of VASP.
```   
    cd <VASP src directory>
    patch -p1 < <path to the interface patch file>
```
- After applying the patch, copy pot_lpcm_k.F and pot_k.F files to the VASP source directory:
- In the original VASP Makefile, put pot_lpcm_k.o pot_k.o object file names before pot.o in that order.
- ``` make clean ```
- ``` make ```

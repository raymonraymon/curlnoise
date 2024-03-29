# curlnoise

Example code corresponding to figures in the paper "Curl noise for
procedural fluid flow", by Bridson, Hourihan, and Nordenstam (SIGGRAPH
2007).

Edit Makefile.defs according to your platform (the defaults are for
Mac OS X). Makefile can be configured for the 2D examples or the
3D example; the code in main() in main2.cpp can be adjusted to run
each of the provided 2D examples.

Run "make depend" followed by "make" (for an unoptimized debug
version) or "make release" (for an optimized release version).

Here's a quick run-down on the source files.  They are not particularly
well documented, and obviously a lot more work is needed to turn
this into a real animation tool, but hopefully it will be clear
enough in relation to the paper. Feel free to email me (rbridson@cs.ubc.ca)
with questions.

bluenoise.h
- provides fast poisson disc sampling in arbitrary dimensions
  (see Bridson's SIGGRAPH 2007 sketch for more details).

curlnoise.h
- provides base classes for the 2d and 3d examples, implementing
  the finite difference evaluation of the curl of the potential but
  leaving the actual potential itself (and seeding of particles
  etc.) to subclasses.

example_*
- example subclasses demonstrating a variety of tricks for
  constructing potentials for fluid-like motion

gluvi.*
- a convenient wrapper around Glut, implementing Maya-like camera
  control (press shift and click or drag with the left, middle, or
  right mouse buttons to see).

interp.h
- utility functions for (bi/tri/quad-)linear interpolation, used
  in Perlin Noise.

main2.cpp
- main code for running the 2D examples. (includes the actual
  drawing, and simple time integration of the particle system)

main3.cpp
- main code for running the 3D example.

noise.*
- a variant of Perlin Noise and Flow Noise in a variety of dimensions.

rigidshape2.h
- a very simple encapsulation of a 2D rigid object (a disc and/or a
  collection of line segments).
  
util.h
- short inline functions for a variety of handy operations, such as
  the ramp() function from the paper.

vec.h
- a wrapper around fixed size vectors (templated on both dimension
  and underlying type).

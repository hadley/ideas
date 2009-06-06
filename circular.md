Circular statistics in ggplot2
==============================

When polar coordinates are used, the usual stats should be replace with circular equivalents, e.g. smoothes, density estimation, contours, ...  Currently ggplot2 lacks both the hooks to do this, and implementation of the circular statistics.

Generally, support for circular statistics in R is not great (although there are two packages, they are incomplete/buggy), and part of this project could be a thorough investigation into circular statistics.

You could also imagine special treatment for circular data in Cartesian coordinate systems - the default behaviour should be to display the data twice, so you can see any 360 degree section.  Some geoms also need tweaks for circular data in polar coordinates - e.g. the line geom should connect the two ends.

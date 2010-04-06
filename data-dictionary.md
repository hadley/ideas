Data dictionary
===============

Tool to make it easier to work with fwf files in R.  Plain text description of file than can be parsed into R to make it easier to read the file.

Should be able to specify:

  * position/width
  * variable name
  * description
  * variable type (optional)
  * factor levels / NA value

  * skip
  * delimiter
  * quotes
  * comments

Replace read.fwf with something much faster.  (Similarly for read.table and read.csv, and provide symmetric outputs including to sqlite)

Should produce better diagnostics for records where the file doesn't conform.  Option to control what to do in those circumstances: skip, error, warn ...

Parse SAS input statements.

In general, it would be very useful to have a small meta language for describing input datasets and extracting just the components that you are interested in.  Should be possible to build on top of work by (e.g.) Robert Kosara (http://eagereyes.org/blog/2009/qnch-data-description-language-for-tabular-data.html) and infochimps.

Also need some tool to inspect data file and make template to complete with additional info:

  * guess delimiters
  * guess if has header or not
  * guess variable types
  * provide space for fuller names, but work without
  * 

Use json?
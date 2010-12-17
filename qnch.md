Data meta-data: qnch
===============
http://eagereyes.org/blog/2009/qnch-data-description-language-for-tabular-data.html

A common way to specify data meta-data (possibly incomplete) in a way that
many different programs can use . Reference implementations in R and Java.
Usable (readable and writable) by both humans and machines.

Implemented in YAML (http://en.wikipedia.org/wiki/YAML, yet another markup language) - it has been designed to be for both humans and computers. Includes features to reduce duplication (data merge and reference)

Can be both many-to-1 or 1-to-many relationship between qnch and data file. One qnch file may combine together multiple files. There may be multiple qnch files for a given input data file, specifying multiple outputs - this is necessary (for example) for microdata census which includes both household level and person level data in the same file.

User level implementation should provide additional options for filtering etc.

# Scope

Is task to make it provide meta-data for clean files, or make it easier to load in messy data? (Probably somewhere in the middle - a data cleaning task might start with initial qnch sketches, then load data, and output with new qnch file). Should work with 90% of data files - but remaining 10% will need special processing. 

Would not, for example, be as complete/powerful as SAS's data statement.  

Focus on getting data into environment, not on cleaning - you may have to do a lot more before it is completely suitable for analysis.

Very very basic subsetting - so you can don't have to describe all thousand variables, and you can crudely filter rows with regular expressions (needed for some data formats).

Maybe needs some way of selecting first unique record for the case where you are making multiple normalised outputs from a single denormalised input.

# Parameters

## File level

* data type
* name
* path or path pattern (if pattern, would automatically create new var) (or should this happen at the implementation level - i.e. to load data you combine data inputs with qnch file - would still be useful to have pointer to data or file name to look for by default)
* source type
* abstract/description etc. (html or markdown?)
* variable defaults?
* template (loaded and merged recursively)
* on-error: skip/error/warn 
* url to download?
* citation
* compression? (or should that be detected automatically?)

## Row level

* skip
* comments
* row pattern
* header? (or would you just use skip = 1?)

## Variable level

* abbreviated (variable) name
* full name
* description
* special values (factor levels / NA value)
* variable type 
* tag/keyword
* is it measured or id

# Options

## Source types

* fixed: characters
* delimited: delimiter, quoting, escaping
* database: type, host, username, password, database, query
* SPSS?
* SAS?
* HTML?
* XML?
* REST API?

(need some pluggable component at the implementation level - not all will be provided out of the box by all implementations, but all MUST provide fixed and delimited (and database?))

## Variable types

* numeric (number?): special-values
* character
* date: date-format
* categorical (category?): categories
* logical

# Creation

Also need some tool to inspect data file and make template to complete with additional info:

  * guess delimiters
  * guess if has header or not
  * guess variable types
  * provide space for fuller names, but work without

Tool to read SAS input statements?

Machine learning to parse data dictionary.

# Sample data

See DASL (http://lib.stat.cmu.edu/DASL/Datafiles/Cheese.html) + OzDASL for sample datasets that we should be able to read in metadata and convert.  See also CAUSEweb.

See weather data - http://www1.ncdc.noaa.gov/pub/data/ghcn/daily/readme.txt

census data - examples of 800 page data dictionaries.
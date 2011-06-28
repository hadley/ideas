Interactive R CMD check
========================

Aim: take the pain out of package development by providing continuous feedback about how you are doing. Fix problems as they arise rather than all at once when you want to distribute it.

Opinionated software (with my opinions on best practices for package development), but pluggable components so that people can modify it to suit their preferences.

Command line application that sets up package skeleton, designed to work nicely with all of the default pluggable components. Includes git init.

Needs generic caching/dependency framework so that the minimum of work needs to be done on each refresh.

Develop

  * reload R files (in correct collate order)
  * compile and load C code
    * see R CMD shlib
    * inline::cfunction
  * load data
  
Check

  * run tests with test_that / runit / svunit
  * run benchmarking (depends on tests passing)
  * roxygenize to produce man files
  * run all examples in documentation
  * push to windows builder

  * check for T and F
  * check for na.rm = FALSE and drop = FALSE (code in butler?)

  * as many steps of R CMD check as possible

Release

  * push to cran
  * create email for r-announce
  * pre-release: proof read generic announcement, description
  * post-release: tag in repos, update version in description
  * create changelog from scm
  * push to github
  
Probably have to do with a gui
See menu() and select.list() for ui components.
Use dependency description ideas from rake.
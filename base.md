New base
========

Rewrite the base package of R, splitting it up into smaller packages of related functionality:

  * dates (lubridate)
  * strings (stringr)
  * file and directory manipulation
  * data manipulation
  * aggregation
  * linear algebra
  * comparison

Reduce the API surface area and bundle related functions together. Each package would provide overview documentation for how all components fit together.

Rewrite functions to have consistent names and function arguments. Better documentation.

Rewrite with an eye to efficiency and speed. Minimise the amount of C, preferring to implement general methods that can be used by many functions.

Comprehensive test and benchmarking suites.
Better error reporting for ggplot2
==================================

Currently, ggplot2 does a very poor job of responding to user errors.  The purpose of this project is figure out how to do it better.  Things to consider:

 * how to build up a set of test cases that represent common user errors

 * how to respond to inputs that may be errors in some cases and may be desired in others

 * the appropriate level of verbosity: when should problems be silently ignored?  (as currently for lines with <2 points, functions in aesthetic specifications)  Should there be an equivalent for na.rm for errors?
 
 * using R scoping rules how can we ensure that aes(colour = blah$blah) is an error, but aes(colour = sqrt(blah)) is not.  Similarly aes(colour = foo) should be an error if foo doesn't exist in the data frame.
 
 * when should errors be reported?  Given that data and aesthetics can be changed up until the last minute (i.e. you might build up a plot with no data and then add it just prior to plotting) when is the best time to report errors?

(More appropriate for a computer science student)
Behaviour based testing for R
==============================

Need a nice dsl

Review: 

  * interesting ruby testing libraries: rspec, shoulda
  * existing R testing libraries: RUnit, svUnit
  * are Revolutions doing anything related?
  
Should:

* be able to watch a directory of tests and a directory of code, and rerun tests whenever either changes
* describe strategy for testing that integrates with usual R testing cycle, but can also be run independently
* be fast
  
Ideas
-----

* `%should%`, `%should_equal%` etc
      a %should_equal% b
      a %should% equal(b)
* vs assert_equal(a, b) or assert equal(a, b)
* test function
      
Questions
-----------

* how can we create an elegant testing DSL given the limitations of R's parser?

* how should non-class based methods be split up?

* what sort of output should assertions return? only failing tests & errors? brief? verbose?  how to weight up good feeling of many passing tests with seeing what actually needs to be fixed?

* how to sandbox tests?  how to make sure lingering function defintions/packages loaded don't affect the tests?  (work in clean environment?  advise on quitting R before rerunning?)

* how can tests be self documenting?   `should "return its full name"`

* can we (by using codetools) only rerun tests that are affected by the changes we made?
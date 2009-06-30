Behaviour based testing for R
==============================

Need a nice dsl

Interesting ruby testing libraries
* rspec
* shoulda
  
Should:
* be able to watch a directory of tests and a directory of code, and rerun tests whenever either changes
* describe strategy for testing that integrates with usual R testing cycle, but can also be run independently
* be fast
  
Ideas:
* %should%, %should_equal% etc
    a %should_equal% b
    a %should% equal(b)
* vs assert_equal(a, b) or assert equal(a, b)
* test function
      
Questions:
* how should non-class based methods be split up?
* what sort of output should assertions return?
* how to sandbox tests?
* how can tests be self documenting?   should "return its full name"
* 
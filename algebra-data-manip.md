# Algebra of data manipulation

Should be able compile to be more efficient.  e.g. it shouldn't matter when you specify subsetting - it should be the first operation performed.  Need to talk to a good CS/DSL person about this - could be interesting CS project.

# Verbs

Verbs operate on the current dataset and return a data set: 

* `_filter`
* `_mutate`
* `_arrange`
* `_summarise`

Also need some generic verbs for producing other types of objects: list,  vector/matrix/array, and nothing.

# Adverbs

Adverbs modify the operation of verb, conceptually by splitting the dataset, feeding each piece in turn and combining.  In practice, probably need optimised code to do more efficiently - part of compilation could be figuring out types so output structures can be created once and then modified in place.

* `_by`

by + transform = col-wise transform
by + subset = calculate condition and then subset once?
by + arrange = arrange
by + summarise = col-wise summary

Do we need notation to specify whether a name is a variable or a value? const? I?  Would make environment look up much eaiser

# Conjunctions

Conjunctions combine multiple datasets - as well as the active dataset, they need another dataset to modify it with.

* `_join`
* `_match`

# Implementation

S4 classes so can take advantage of proper operator dispatch:

  * verb + verb -> compound verb
  * verb + data -> data

What operator to use?

* `+` - operation isn't commutative, plus doesn't feel like a good fit
* `&` - perhaps, conveys sequential modification - do this AND that
* `<=`, `=>` - conveys directional transformation


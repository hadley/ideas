High-level gui library for R
============================

Should be based on Qt.  Takes the best features of gWidgets and extends them in a way that isn't possible when you have to support multiple toolkits. (Another DSL).  Uses mutable objects to create DSL.

Ideas
-----

See mutatrGui for basics.

Higher-level interface should be centred around concept of typed variables:

* continuous value: slider, spin box
* boolean: check box, toggle button
* small set of discrete values: radio buttons, list box (1 row table), combo box
* large set: text box with autocomplete
* multiselect: checkbox group, table, ...

Should separate between value (what computer uses) and label (what humans use).


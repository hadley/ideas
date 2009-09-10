High-level gui library for R
============================

Should be based on RGtk2, or other single library.  Takes the best features of gWidgets and extends them in a way that isn't possible when you have to support multiple toolkits. (Another DSL)

Ideas
-----

* use method chaining to make it easier to make multiple changes
    slider$
      set_value(30)$
      set_height(20)

  This moves away from R's usual object semantics, but immutable objects are not well suited for modelling things that are clearly mutable.
      

* structure of code (e.g. with indentation) should mimic structure of eventual gui
    container$
      add_child(x)$
      add_child(new_group()$
        add_child("Hi")$
        add_button("Click me")
      )
* use mvc ideas to connect gui elements to R objects
* should be easy to add handlers to different events

Higher-level interface should be centred around concept of typed variables:

* continuous value: slider, spin box
* boolean: check box, toggle button
* small set of discrete values: radio buttons, list box (1 row table), combo box
* large set: text box with autocomplete
* multiselect: checkbox group, table, ...

Should separate between value (what computer uses) and label (what humans use).

Life and Death of a jQuery Programmer
====================================


Timeline / Content Plan
-----------------------

1. __Uses plugins (Birth)__
   * jQuery is easy to start
   * jQuery has plugins for just about everything
   * Plugins do much more that than you need
   * Plugins are easy to install
   * Plugins have customizable options
   * Plugins only customize so far
2. __Writes own code__
   * Plugin’s are all or nothing. Poor design with “private” functionality doesn’t allow reuse
   * Throws plugin away and writes own solution
   * Solution is imperative and non-declarative, hard to read and understand what it does
   * Callback nightmare
   * Callbacks are extracted in functions for better readability
3. __Writes plugin__
   * “Global variables” and no certain state
   * Extract code in a plugin to better preserve scope
   * Business logic is mixed on the DOM
4. __Uses objects__
   * Creates objects to hold data and business logic
   * Now it’s easy to tell what are the units of logic
5. __Unit test__
   * Start testing code behavior with BDD
   * Start writing business logic first then UI
6. __Ditches jQuery (Death)__
   * New design approach leaves jQuery to a secondary tool
   * jQuery becomes too expensive at 31Kb
   * Visits [microjs.com][microjs]
   * Dies

[microjs]: http://microjs.com


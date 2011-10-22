Life and Death of a jQuery Programmery
====================================


Timeline / Content Plan
-----------------------

1. __Uses plugins (Birth)__
   * jQuery is easy to start
     jQuery is possibly the most used frontend library out there, it's present in everything from simple blog templates to huge e-commerce websites. "Write less, do more" is its motto and because of that the barrier to entry is very small and the user base already so big, there are plenty of tutorials out there to help you accomplish anything on a web page. 
   * jQuery has plugins for just about everything
     Because of its tremendous success, a huge community of users support the project by creating plugins that ease the development of all sorts of widgets and UI functionality. Slideshow, carousel, modal window, zoom, slider... and much more, all available for easy/oneliner integration 
   * Plugins are easy to install
     Plugins are generally easy to use and integrate. They consist in a javascript file, and sometimes some stylesheets and images too, and all you have to do is activate it, by generally just calling a single method in a selector set `$("#content").exampleModal();`.
   * Plugins have customizable options
     Plugins provide options by which you can customize some of its properties, like which selector it should consider for buttons, or what kind of animation it should use for image transition, these are passed on to the plugin setup call.
   * Plugins only customize so far
2. __Writes own code__
   * Plugins do much more that than you need
   * Plugin’s are all or nothing. Poor design with “private” functionality doesn’t allow reuse
     Plugins are built to have a single public interface, which is the plugin method, and everything else is left on a closed scope, which only that function has access to. It makes it impossible to take advantage of javascript's dynamic prototype, to maybe change a functionality to adequate to your needs, and also to reuse bits of code, like only get the sliding animation from a gallery plugin and reuse on a rotating banner. You either use it all, or you use something else
   * Throws plugin away and writes own solution
     In the search of a more granular control and also reusability of logic, plugins start to give space to specific solutions for the application
   * Solution is imperative and non-declarative, hard to read and understand what it does
     The code basically becomes a series of instructions and DOM updates happening for each event or for each DOM element in a set. The set of instructions don't really make sense on an overview and has to be read to be understood, this makes debugging more complex. Also, the solution have no identity, code generally looks the same throughout different solutions
   * Callback nightmare
     Because the code is oriented by UI events and is also heavy on functional loops and maps, callbacks start to emerge everywhere and soon there are 4 or 5 levels of indentation floating around each with its own closure and possibly vars with same names. Dollar-variables also start showing up and deeper functions access variables from upper levels... hell
   * Callbacks are extracted in functions for better readability
     Extracting callbacks makes code more linear and declares better what is supposed to happen when a block of code is being executed. It helps on readability and also on debugging. It's also a step forward on reusability as you can pass functions around to different events
3. __Writes plugin__
   * “Global variables” and no certain state
   * Extract code in a plugin to better preserve scope
   * Business logic is mixed on the DOM
     Data and logic start to depend on the DOM, by extense use of `jQuery.data` and also by only being able to interact with the application by the use of its GUI. This makes testing a pain as you always have to refresh the browser and click around to see whether the outcomes are right
4. __Uses objects__
   * Creates objects to hold data and business logic
   * Now it’s easy to tell what are the units of logic
5. __Unit test__
   * Start testing code behavior with BDD
   * Start writing business logic first then UI
6. __Ditches jQuery (Death)__
   * New design approach leaves jQuery to a secondary tool
     Instead of having your entire code scoped and based off of jQuery, business logic is now separated and UI code is mostly content updates and animation, which are really trivial to the application as a whole and can be abstracted away in a deep shady place
   * jQuery becomes too expensive at 31Kb
     As jQuery dependency decreases, its size becomes too expensive to be used in just a few lines. It's also too powerfull for the very simple usage the application needs
   * Visits [microjs.com][microjs]
     There are tons of mini, micro, small javascript libs that focus on just one part of browser or DOM interaction and try to do it in a simple way. It helps improving performance and also to allow better control of what you are using under the hood. Sometimes you can even get a syntax/interface that better suits the application  
   * Dies

[microjs]: http://microjs.com


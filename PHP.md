### Comparison Criteria

#### Language purpose/genesis
  ** Why was the language created?**
  
  PHP was created as a server-side scripting language designed primarily for web development but also used as a general-purpose programming language. 
  
  ** What problems was the language trying to address?**
  
  Wanted to work with web forms and communicate with databases
  
  ** Is the language a reaction to a previous language or a replacement for another language?**
  
  It is a reaction to the previous language C, in which he wrote CGI programs to maintain his webpage
  
#### Unique features of the language
  ** Does the language have any particularly unique features?**
  
  Can be embedded into HTML using <?php [insert code] ?>
  
#### Name spaces
  ** How are name spaces implemented?**
  
         <?php
         namespace MyProject;
         ?>
  
  ** How are name spaces used?**
  
 To solve two problems that authors of libraries and applications encounter when creating re-usable code elements such as classes or functions: name collisions and ability to alias, improving readability.
  
#### Types
    ** What types does the language support?**
    
    String,
    Integer,
    Float (floating point numbers - also called double),
    Boolean,
    Array,
    Object,
    NULL,
    Resource
    
    ** Are both reference and value types supported?**
    
    
    
    ** Can new value types be created?**
    
    
    
#### Classes
  ** Defining**
  
  Unless autoloading is used, then classes must be defined before they are used.
  
        <?php
        class SimpleClass
        {  
          //insert code 
        }
        ?>
  
  ** Creating new instances**
  
        <?php
        $instance = new SimpleClass();

        // This can also be done with a variable:
        $className = 'SimpleClass';
        $instance = new $className(); // new SimpleClass()
        ?>
  
  ** Constructing/initializing**
  
        void __construct ([ mixed $args = "" [, $... ]] )
  
        function __construct() {
           print "In BaseClass constructor\n";
           $this->name = "MyDestructableClass";
         }
  
  ** Destructing/de-initializing**
  
        void __destruct ( void )
        
        
        function __destruct() {
          print "Destroying " . $this->name . "\n";
        }
  
#### Instance reference name in data type (class)
  * this?  self?
  
  The pseudo-variable $this is available when a method is called from within an object context.
  
#### Properties
  * Getters and setters...write your own or built in?
  * Backing variables?
  * Computed properties?
### Interfaces / protocols
  ** What does the language support?**
  
  Interfaces
  
  ** What abilities does it have?**
  
  Object interfaces allow you to create code which specifies which methods a class must implement, without having to define how these methods are handled.
  
  ** How is it used?**
  
  Interfaces can be extended like classes using the extends operator.
  
  The class implementing the interface must use the exact same method signatures as are defined in the interface.
  
      interface iTemplate
      { 
       //code
      }


      class Template implements iTemplate
      {
       //code
      }

      interface a
      {
        public function foo();
      }

      interface b extends a
      {
       public function baz(Baz $baz);
      }

      interface c extends a, b
      {
       public function baz();
      }
      
      
#### Inheritance / extension

PHP makes use of this principle in its object model. 

The subclass inherits all of the public and protected methods from the parent class. Unless a class overrides those methods, they will retain their original functionality.

    class Bar extends Foo

#### Reflection
  * What reflection abilities are supported?
  
  PHP 5 comes with a complete reflection API that adds the ability to reverse-engineer classes, interfaces, functions, methods and extensions. Additionally, the reflection API offers ways to retrieve doc comments for functions, classes and methods.
  
  * How is reflection used?
  
  From Shell (a Terminal)
  
  Through different classes such as Reflection, ReflectionClass, ReflectionMethod, Reflector interfaces, etc.
  
#### Memory management
  * How is it handled?
  * How does it work?
  * Garbage collection?
  * Automatic reference counting?
#### Comparisons of references and values
  * How are values compared? (i.e. comparing two strings)
#### Null/nil references
  ** Which does the language use? (null/nil/etc)
  
  NULL
  
  ** Does the language have features for handling null/nil references?
  
  PHP has is_null() and unset() functions to check if something is null or remove null, be null casting is not allowed.
  
#### Errors and exception handling

      "die()" statements

      error_function(error_level,error_message,error_file,error_line,error_context)

      error_log() 

      trigger_error()

      set_error_handler("customError");
      
  
  PHP also has try, catch, finally for exception handling.

* Lambda expressions, closures, or functions as types
* Implementation of listeners and event handlers
* Singleton
  * How is a singleton implemented?
  * Can it be made thread-safe?
  * Can the singleton instance be lazily instantiated?
* Procedural programming
  * Does the language support procedural programming?
* Functional programming
  * Does the language support functional programming?
* Multithreading
  * Threads or thread-like abilities
  * How is multitasking accomplished?

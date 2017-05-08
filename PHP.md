# Comparison Criteria

## Language purpose/genesis
  **Why was the language created?**
  
  PHP was created as a server-side scripting language designed primarily for web development but also used as a general-purpose programming language. 
  
  **What problems was the language trying to address?**
  
  Wanted to work with web forms and communicate with databases
  
  **Is the language a reaction to a previous language or a replacement for another language?**
  
  It is a reaction to the previous language C, in which he wrote CGI programs to maintain his webpage
  
## Unique features of the language
  **Does the language have any particularly unique features?**
  
  Can be embedded into HTML using <?php [insert code] ?>
  
  Cookies
  
  Sessions
  
  Database connections
  
  HTTP authentication
  
  Forms
  
  XForms
  
## Name spaces
  **How are name spaces implemented?**
  
         <?php
         namespace MyProject;
         ?>
  
  **How are name spaces used?**
  
 To solve two problems that authors of libraries and applications encounter when creating re-usable code elements such as classes or functions: name collisions and ability to alias, improving readability.
  
## Types
   **What types does the language support?**
    
 String, Integer, Float (floating point numbers - also called double),
  Boolean,
 Array,
 Object,
 NULL,
Resource
    
  **Are both reference and value types supported?**
    
A PHP reference is an alias, which allows two different variables to write to the same value.
    
 **Can new value types be created?**
    
No
    
    
## Classes
  **Defining**
  
  Unless autoloading is used, then classes must be defined before they are used.
  
        <?php
        class SimpleClass
        {  
          //insert code 
        }
        ?>
  
  **Creating new instances**
  
        <?php
        $instance = new SimpleClass();

        // This can also be done with a variable:
        $className = 'SimpleClass';
        $instance = new $className(); // new SimpleClass()
        ?>
  
  **Constructing/initializing**
  
        void __construct ([ mixed $args = "" [, $... ]] )
  
        function __construct() {
           print "In BaseClass constructor\n";
           $this->name = "MyDestructableClass";
         }
  
  **Destructing/de-initializing**
  
        void __destruct ( void )
        
        
        function __destruct() {
          print "Destroying " . $this->name . "\n";
        }
  
## Instance reference name in data type (class)
  **this?  self?**
  
  The pseudo-variable $this is available when a method is called from within an object context.
  
## Properties
  **Getters and setters...write your own or built in?**
  
  Overloading in PHP provides means to dynamically "create" properties and methods. These dynamic entities are processed via magic methods one can establish in a class for various action types.
  
  __set() is run when writing data to inaccessible properties.
  
  __get() is utilized for reading data from inaccessible properties.
  
  Static properties are accessed by using the :: (Double Colon): self::$property
  
  **Backing variables?**
  
  Not useful.
  
  **Computed properties?**
  
  They are defined by using one of the keywords public, protected, or private, followed by a normal variable declaration.
  
  If you declare a property using var instead of one of public, protected, or private, then PHP 5 will treat the property as if it had been declared as public.
  
## Interfaces / protocols
  **What does the language support?**
  
  Interfaces
  
  **What abilities does it have?**
  
  Object interfaces allow you to create code which specifies which methods a class must implement, without having to define how these methods are handled.
  
  **How is it used?**
  
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
      
      
## Inheritance / extension

PHP makes use of this principle in its object model. 

The subclass inherits all of the public and protected methods from the parent class. Unless a class overrides those methods, they will retain their original functionality.

    class Bar extends Foo

## Reflection
  **What reflection abilities are supported?**
  
  PHP 5 comes with a complete reflection API that adds the ability to reverse-engineer classes, interfaces, functions, methods and extensions. Additionally, the reflection API offers ways to retrieve doc comments for functions, classes and methods.
  
  **How is reflection used?**
  
  From Shell (a Terminal)
  
  Through different classes such as Reflection, ReflectionClass, ReflectionMethod, Reflector interfaces, etc.
  
## Memory management
  **How is it handled?**
  
  Tracking allocations allow the memory manager to avoid leaks, a thorn in the side of most Hackers. When PHP is built in debug mode (--enable-debug), detected leaks are reported, in a perfect world they would never get to deployment.
  
  The memory manager is the part that allows a hard limit on memory usage for each instance of PHP
  
  The engines memory management functions do not return NULL upon failure, if memory cannot be allocated at runtime, the engine bails and raises an error.
  
  **How does it work?**
  
  void *emalloc(size_t size)
  
  void *ecalloc(size_t nmemb, size_t size)
  
  void *erealloc(void *ptr, size_t size)
  
  void efree(void *ptr)
  
  void *safe_emalloc(size_t nmemb, size_t size, size_t offset)
  
  char *estrdup(const char *s)
  
  char *estrndup(const char *s, unsigned int length)
  
  **Garbage collection?**
  
  Garbage cycles
  
  Garbage cycles can only be created when a refcount argument is decreased to a non-zero value. Secondly, in a garbage cycle, it is possible to discover which parts are garbage by checking whether it is possible to decrease their refcount by one, and then checking which of the zvals have a refcount of zero.
  
   gc_collect_cycles() 
  
  **Automatic reference counting?**
  
  A PHP variable is stored in a container called a "zval". A zval container contains, besides the variable's type and value, two additional bits of information.
  
  The first is called "is_ref" and is a boolean value indicating whether or not the variable is part of a "reference set". With this bit, PHP's engine knows how to differentiate between normal variables and references.
  
  This second piece of additional information, called "refcount", contains how many variable names (also called symbols) point to this one zval container.
  
## Comparisons of references and values
  **How are values compared? (i.e. comparing two strings)**
  
  $a == $b	Equal	TRUE if $a is equal to $b after type juggling.
  
  $a === $b	Identical	TRUE if $a is equal to $b, and they are of the same type.
  
## Null/nil references
  **Which does the language use? (null/nil/etc)**
  
  NULL
  
  **Does the language have features for handling null/nil references?**
  
  PHP has is_null() and unset() functions to check if something is null or remove null, be null casting is not allowed.
  
## Errors and exception handling

   "die()" statements

    error_function(error_level,error_message,error_file,error_line,error_context)

    error_log() 

    trigger_error()

   set_error_handler("customError");
      
  
  PHP also has try, catch, finally for exception handling.

## Lambda expressions, closures, or functions as types

Anonymous functions, also known as closures, allow the creation of functions which have no specified name. They are most useful as the value of callback parameters, but they have many other uses.

Anonymous functions are implemented using the Closure class.

## Implementation of listeners and event handlers

xml_set_element_handler()

xml_set_character_data_handler()

xml_set_processing_instruction_handler()

xml_set_default_handler()

xml_set_unparsed_entity_decl_handler()

xml_set_notation_decl_handler() .. etc.

## Singleton
  **How is a singleton implemented?**
  
  The singleton pattern is useful when we need to make sure we only have a single instance of a class for the entire request lifecycle in a web application. 
  
  Uses getInstance() and static variables
  
  **Can it be made thread-safe?**
  
  Yes
  
  **Can the singleton instance be lazily instantiated?**
  
  You should be wary when using the singleton pattern, as by its very nature it introduces global state into your application, reducing testability.
  
       use \LazyProperty\LazyPropertiesTrait;

       protected $userRepository;

      public function __construct()
       {
        // ...
        // mind this - we are marking "userRepository" as lazy
        $this->initLazyProperties(['userRepository']);
      }

      public function register($user)
      {
          // ...
        // now use the property directly
        $this->userRepository->add($user);
        // ...
      }

  
## Procedural programming
  **Does the language support procedural programming?**
  
  Yes
 
 Normal: 
      $mysqli = new mysqli("localhost", "my_user", "my_password", "world");
  
 Procedural:     
      $link = mysqli_connect("localhost", "my_user", "my_password", "world");
  
 Normal:      
      $mysqli->query("CREATE TEMPORARY TABLE myCountry LIKE Country");

 Procudural:
       mysqli_query($link, "CREATE TEMPORARY TABLE myCountry LIKE Country");
 
## Functional programming
  **Does the language support functional programming?**
  
  Yes
  
      <?php
      function foo($arg_1, $arg_2, /* ..., */ $arg_n)
      {
         echo "Example function.\n";
         return $retval;
      }
      ?>
   
## Multithreading
  **Threads or thread-like abilities**
  
  The Thread class enables for threads to be created by simply extending it and implementing a run method
  
  The Threaded class forms the basis of the functionality that allows pthreads to operate.
  
      Thread extends Threaded implements Countable , Traversable , ArrayAccess {
      }
  
  **How is multitasking accomplished?**
  
  pthreads is an object-orientated API that provides all of the tools needed for multi-threading in PHP
  
  The Pool class is used to create a group of workers to distribute Threaded objects amongst them. It is the easiest and most efficient way of using multiple threads in PHP applications.
  
  Any objects that are intended for use in the multi-threaded parts of your application should extend Threaded.

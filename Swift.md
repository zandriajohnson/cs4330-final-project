### Comparison Criteria

* Language purpose/genesis
  * Why was the language created?
  
  Swift is designed to work with Apple's Cocoa and Cocoa Touch frameworks and the large body of extant Objective-C (ObjC) code written for Apple products.
  
  * What problems was the language trying to address?
  
  The goal of the Swift project is to create the best available language for uses ranging from systems programming, to mobile and desktop apps, scaling up to cloud services. Most importantly, Swift is designed to make writing and maintaining correct programs easier for the developer. Swift is intended to be more resilient to erroneous code ("safer") than Objective-C, and more concise.
  
  * Is the language a reaction to a previous language or a replacement for another language?
  
  Swift was written  as a reaction and improvemnt language taking ideas from Objective-C, Rust, Haskell, Ruby, Python, C#, CLU, and many others. 
  
* Unique features of the language
  * Does the language have any particularly unique features?
  
Closures unified with function pointers
Tuples and multiple return values
Generics
Fast and concise iteration over a range or collection
Structs that support methods, extensions, and protocols
Functional programming patterns, e.g., map and filter
Powerful error handling built-in
Advanced control flow with do, guard, defer, and repeat keywords
  
* Name spaces
  * How are name spaces implemented?
  * How are name spaces used?
  
  Swift doesn't support namespaces but as a solution you can create namespaces with stuck. 
  
* Types
    * What types does the language support?
    
    Swift supports: inferred, optional, enumeration, value, numeric, no-objective optional, and generic types. 
    
    * Are both reference and value types supported?
    
    Yes swift supports both value and reference types.
    
    * Can new value types be created?
    
    No they are copied when they are passed around in code. 
    
* Classes
  
**Defining**
 
        Class classname {
        
         Definition 1
         Definition 2
         --- 
         Definition N
         
        }
 
  * Creating new instances
  
  Very similar to creating structioners and classes
  
  **Example**
  
      let someResolution = Resolution()
      let someVideoMode = VideoMode()
  
  * Constructing/initializing
  
  **Syntax**
      
      init() {
       //New Instance initialization goes here
      }


**Example**

    struct rectangle {
    
     var length: Double
     var breadth: Double
     
     init() {
      length = 6
      breadth = 12
      }
     
     }
    
    var area = rectangle()
    println("area of rectangle is \(area.length*area.breadth)")
  
  * Destructing/de-initializing
  
  **Example**
  
      var counter = 0;  // for reference counting
      class baseclass {
       init() {
        counter++;
       }
       deinit {
        counter--;
       } 
      }

      var print: baseclass? = baseclass()
      println(counter)
      print = nil
      println(counter)
  
* Instance reference name in data type (class)
  * this?  self?
  **self**
  
      class PersonClass {
       var name: String
       init(name: String) {
         self.name = name
       }
      }
      var person = PersonClass(name: "John Doe")
  
  
* Properties
  * Getters and setters...write your own or built in?
  
  Build in.
  
  * Backing variables?
  
You can use instance variables as a backing store for the values stored in a property. Swift unifies these concepts into a single property declaration. A Swift property does not have a corresponding instance variable, and the backing store for a property is not accessed directly. This approach avoids confusion about how the value is accessed in different contexts and simplifies the property’s declaration into a single, definitive statement.
  
  * Computed properties?
  
  Computed properties calculate (rather than store) a value. Computed properties are provided by classes, structures, and enumerations. Stored properties are provided only by classes and structures.
  
* Interfaces / protocols
  * What does the language support?
  
  Swift supports inferred types to make code cleaner and less prone to mistakes, and modules eliminate headers and provide namespaces. Also, swift supports five access control levels for symbols: open, public, internal, fileprivate, and private. Unlike many object-oriented languages, these access controls ignore inheritance hierarchies.
  
  * What abilities does it have?
  
A key element of the Swift system is its ability to be cleanly debugged and run within the development environment, using a read–eval–print loop (REPL), giving it interactive properties more in common with the scripting abilities of Python than traditional system programming languages.
  
  * How is it used?
  
  Just like Java interfaces, but it's called a protocol in swift
  
      protocol MyEngine {
        func doWork() -> Bool
      }
  
* Inheritance / extension

A subclass inherits the properties, methods and functions of its base class. To define a subclass ':' is used before the base class name.

    class StudDetails {
       var mark1: Int;
       var mark2: Int;

       init(stm1:Int, results stm2:Int) {
          mark1 = stm1;
          mark2 = stm2;
       }

       func print() {
          println("Mark1:\(mark1), Mark2:\(mark2)")
       }
     }

    class display : StudDetails {
       init() {
          super.init(stm1: 93, results: 89)
       }
    }

    let marksobtained = display()
    marksobtained.print()

* Reflection
  * What reflection abilities are supported?
  
  Swift no longer has reflection but the struct Mirror can resemble Mirror. 
  
  * How is reflection used?
  
  Reflection in Swift is easy using the struct Mirror, with it we can inspect the names and types of properties in an instance of a struct or an instance of a class.
  
* Memory management
  * How is it handled and how does it work?
  
  Swift uses Automatic Reference Counting (ARC) to track and manage an app’s memory usage. In most cases, this means that memory management “just works” in Swift, and you do not need to think about memory management yourself. ARC automatically frees up the memory used by class instances when those instances are no longer needed.
  
* Comparisons of references and values
  * How are values compared? (i.e. comparing two strings)
  
  Use the "==" to compare values ex:
  
      if s1==s2 {
          print("S1 is the same as S2")
      }
      else {
          print("S1 is not the same as S2")
      }
  
* Null/nil references
  * Which does the language use? (null/nil/etc)
  
  Swift uses nil. 
  
  * Does the language have features for handling null/nil references?
  
 Optional chaining is a process for querying and calling properties, methods, and subscripts on an optional that might currently be nil. If the optional contains a value, the property, method, or subscript call succeeds; if the optional is nil, the property, method, or subscript call returns nil. Multiple queries can be chained together, and the entire chain fails gracefully if any link in the chain is nil. 
 
* Errors and exception handling

Error handling is the process of responding to and recovering from error conditions in your program. Swift provides first-class support for throwing, catching, propagating, and manipulating recoverable errors at runtime.

Some operations aren’t guaranteed to always complete execution or produce a useful output. Optionals are used to represent the absence of a value, but when an operation fails, it’s often useful to understand what caused the failure, so that your code can respond accordingly.

As an example, consider the task of reading and processing data from a file on disk. There are a number of ways this task can fail, including the file not existing at the specified path, the file not having read permissions, or the file not being encoded in a compatible format. Distinguishing among these different situations allows a program to resolve some errors and to communicate to the user any errors it can’t resolve.

    enum VendingMachineError: Error {
        case invalidSelection
        case insufficientFunds(coinsNeeded: Int)
        case outOfStock
    }
    
    throw VendingMachineError.insufficientFunds(coinsNeeded: 5)

* Lambda expressions, closures, or functions as types

Closures

* Implementation of listeners and event handlers

      class Event<T> {

        typealias EventHandler = T -> ()

        private var eventHandlers = [EventHandler]()

        func addHandler(handler: EventHandler) {
          eventHandlers.append(handler)
        }

        func raise(data: T) {
          for handler in eventHandlers {
            handler(data)
          }
        } 
      }

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

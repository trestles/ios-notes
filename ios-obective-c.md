
Objective C

### Objective-C

* interface (.h) / implementation (.m) PF 77-80
    - in iterface file:
       - public variables  
         - @property  
         - strong / weak   
       - public methods (both instance and class)
         - class methods have hard time managing notion of self
       - conforms to protocol information

   

- in implementation file:   
  private variables  
  method implementations

* Just Enough C PF3-32
* Object-Based Programming PF33-44
* Objective C Objects and Messages PF45-73

* Class Methods PF81
* The Secret Life of Classes PF82

* protocols PF272
* Informal Protocols PF276
* Optional Methods PF277

* Property Lists PF292
* The Secret Life of NSObject PF293

* Communication Between Objects PF373
  - Visibility by Instantiation PF373
  - Visibility by Relationship PF376
  - Global Visibility PF377
  - Notifications PF378
  - Key-Value Observing PF379
  - Model-View-Controller PF385




- declaring a method PF54
- Nesting method calls PF55
- parameter lists PF57
- messages to nil PF59   
- Unrecognized selectors PF60
- Typecasting and the id type PF61
- Messages as Data Type PF65
- C Functions PF67
- CFTypeRefs PF68
          
- calling methods:
  - return type, named arguments

- id type
- casting

- The Secret Life of Classes PF82
- The Global Namespace PF84

#####How Instances are created 

* Ready-Made Instances 
* Instantiation from Scratch PF86
  * iniialization PF87
  * designated initializer PF89
* Nib-based Instantiation PF90
* Polymorphism PF91
* The Keyword self PF93
* The Keyword Super PF97
* Instance Variables and Accessors 
* Key-Value Coding PF101; PTL395-401
* Properties PF103
* How to write an initializer PF104
* Referring to Instances PF108


* Subclassing PF265
* Categories PF268
  * splitting a class PF270 
  * class extensions PF271



- blocks IA335-7, PF69-72
   when defining a block, you're actuall creating a *block literal* ... The term literal comes from the fact that you're writing data "literally" into your code 

```
^(int a, int b)
 {
   int powres = a ** b;
   return powres;
}
```

differences with C funtion  

1. carat symbol preceding 
2. return types are automatically infeffered when not defined
3. there is no function name; we say that block literals are anonymous

as with function and method definitions, the braces indicate the start and end of the block. Blocks can also take arguments and return values just like methods and functions. In a nutshell, block literals encapsulate a bunch of code the same way C functions do, but they also hold some really useful features. 

####Block Pointers
A block pointer isn't any different from an object pointer in the way that you can pass it to functions or create functions that return blocks. In following example:

```
int(^pow)(int, int) = ^(int a, int b)
{
  int powres= a ** b;
  return powres;
}

```

The carat symbol ^ replaces the start * that you usually use for declaring variable pointers. The meaning is the same, but by using the caret symbol you're telling the compiler that instead of pointing to  a value, you're pointing to a block of code. 

Blocks are defined in a local scope. In other words, blocks can be anywhere a variable can. The scope is very important when defining blocks because you can access variables from the same enclosing scope where the block is defined. Here's an example: 

```
-(void)exampleMethod
{
  int variableInsideMethod=10;
  void(^exampleBlock)(void)=^(void){
    NSLog(@"can access %d", variableInsideMethod);
  }
}
```

####Block Invocation IA336
shown:

- how to declare a block
- how their pointers are assigned

important to understand that, so far, the code inside your blocks hasn't executed at all. 

blocks ARE invoked via:

```
int pow_result=pow(3,4);
```
exact same syntax as function calls. Blocks return a specific type (or none) and take arguments the same way a c function does. 

####Common Usage IA336

A block represents a unit of executable code that can capture variables of the surrounding scope. This makes blocks ideal for asynchronous invocation; in fact, blocks are used extensively when writing  (1) asynchronous tasks. Also, very handy when it comes to writing (2) multithreading operations. 

Other typical usages:

- running code when an asynchronous task is completed (for example, an HTTP request)
- handling errors on asynchronous calls
- handling asynchronous notifications
- as lambda functions, for iterations (sorting, enumerations, and the like)
- UIView animations and transitions

####Understanding Automatic Reference Counting

######Properties and Attributes  IA340, PF103 - PF104
strong / weak / copy / assign - define how memory is managed on the setter. You use these attributes to tell the compiler about the relationships that you expect. Strong references are a way of owning the variable, meaning that as long as the instance holding the property is alive, the variable will be as well. Weak references can be removed from memory at any time, and the instance has no control over that. 

A retain cycle is a situation in which object A retains object B and object B retains object A at the same time. 

Retain cycles are somewhat dangerous with blocks because all the variables from the surrounding scope you use inside the block will be retained - for example:

```
[self someMethodWithBlock: ^{
  [self someOtherMethod];
}]
```

1.1 Implementing and Using Custom Objects  
1.2 Allocating and Initializing Objects  
1.3 Defining two or more methods with the same name in an Object  
1.4 Defining and Accessing Properties  
1.5 Managing Properties Manually  
1.6 Reusing a Block of Code
1.7 Communicating with Objects  
1.8 Invoking the Selectors of an Object Dynamically  
1.9 Managing Memory with the iOS SDK  
1.10 Managing untyped Objects  




- Static Analyzer PF227
- Clean PF229
- Running on a Device PF230
- Gauges and Instruments PF238



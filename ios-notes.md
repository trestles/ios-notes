Goal of this is to provide notes to someone who probably codes predominantly in something else but also does iOS work. I like starting with the simplest example to show a concept / pattern and hopefully be able to flesh it out.

IOS 7 in Action - IA  
iOS 7 by Tutorials - IT  
NSHipster Fake Book - FB  
Apple Docs:
   View Controller Programming Guide - AVC

Programming iOS7 - P  
iOS7 Programming Fundamentals PF
iOS7 Programming Pushing the Limits - PTL   
iOS 6 Coobook IC

###rebuild iOS knowledge
Objective C - background: instance variables, methods, class methods
   - protocols IA54-5
      - specify in interface
      - methods would be required
      - to create a protocol

   - extensions - monkeypatching for Objective-C
MVC

### Objective-C

* interface (.h) / implementation (.m) PF 77-80
    - in iterface file:
       public variables  
         @property  
         strong / weak   
       public methods (both instance and class)
         class methods have hard time managing notion of self
       conforms to protocol information

   

    - in implementation file:   
      private variables
      method implementations

* Class Methods PF81
* The Secret Life of Classes PF82

* protocols PF272
* Informal Protocols PF276
* Optional Methods PF277

* Property Lists PF292
* The Secret Life of NSObject PF293

Communication Between Objects PF373
  Visibility by Instantiation PF373
  Visibility by Relationship PF376
  Global Visibility PF377
  Notifications PF378
  Key-Value Observing PF379
  Model-View-Controller PF385




declaring a method PF54
Nesting method calls PF55
parameter lists PF57
messages to nil PF59   
Unrecognized selectors PF60
Typecasting and the id type PF61
Messages as Data Type PF65
C Functions PF67
CFTypeRefs PF68
          
  calling methods:
    return type, named arguments

  id type
  casting

The Secret Life of Classes PF82
The Global Namespace PF84

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
* Key-Value Coding PF101
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




2. controllers
   instantiating VCs
     - initWithCoder
     - initWithNibName - why?

   UIViewController - lifecycle
     - Instantiating a Storyboard’s View Controller Programmatically AVC
     - Segues Automatically Instantiate the Destination View Controller AVC
        - where in the VC lifecycle?
     - Transitioning to a New Storyboard Requires a Programmatic Approach AVC
     - Displaying a View Controller’s Contents Programmatically AVC
        how to show:
           1. Make the view controller the root view controller of a window
           2. Make it a child of a visible container view controller
           3. Present it from another visible view controller
           4. Present it using a popover (iPad only)
      Anatomy of a Content View Controller AVC
      Inititalizing A View Controller
        Initializing a View Controller Loaded from a Storyboard  
        Initializing View Controllers Programmatically
      - Managing Memory Efficiently AVC
      - Responding to Display-Related Notifications AVC
         Determining Why a View’s Appearance Changed
      - Using View Controllers in the Responder Chain AVC  
      - Creating Custom Seques AVC
             
   UINavigationController - embed in
     UINavigationItem
     UITabBarItem, UIBarButtonItem
     
```
     // from http://stackoverflow.com/questions/24961671/push-segues-can-only-be-used-by-uinavigationcontroller-error
     UINavigationController *recordNavigationController = (UINavigationController*)[self.storyboard instantiateViewControllerWithIdentifier:@"RecordNavigationController"];
     self presentViewController:recordNavigationController animated:YES completion:nil];
```

   maintain a reference to controller that displays and holds your tasks:
   @property (weak, nonatomic) id delegate; //IA61  and IA62
   connectiong controllers in storyboard - IA62
     - can be done only in context of Navigation Controller
   prepareForSegue IA64  

2.5.   
##views - UIView, UIControl, UIResponder, 
   subviews, setNeedsDisplay


  * X,Y coordinates
  * initWithFrame



   representing pixels
   capturing events
     - where are actions defined?
     - can handle events in a UIViewController OR in UIView subclasses

  - UIView will delegate much of functionality to Core Animation specifically CALayer
  - CALayer doesn't handle user interaction
  - Each UIview has a `layer` property that is an instance of CALayer (known as the backing layer)
  - UIView is simply a wrapper, providing iOS specific funtionality such as touch handling and high-level interfaces for some of Core Animations low-level functionality
  - "For simple purposes, we don't really need to deal directly"
      - "CALayer has a `contents` property" but must be CGImage"
      - "Core Foundation types behave like Cocoa objects at runtime - known as toll-free-bridging"

4. Events
  - traditionally, events are created and captured at the level of UIViewController
     - can be be created in Storyboard or in code
     - in Storyboard, would need to drag from item to UIViewController
        - does NOT need to have IBAction public interface
     - 
  - selectors
     - example of repeatedly calling selector in IA
     - registering a selector
     - simplest selector example   


##AFNetworking and Networking

classes:

* NSURLConnection
  * AFHTTPRequestOperation
  * AFHTTPRequestOperationManager
  * AFURLConnectionOperation
* NSURLSession
  * AFHTTPSessionManager
  * AFURLSessionManager
* Reachability
  * AFNetworkReachabilityManager
* Security
  * AFSecurityPolicy
* Serialization
  * AFURLRRequestSerialization
  * AFURLResponseSerialization
* Support Files
* UIKit
  * AFNetworkActivityIndicatorManager
  * UIActivityIndicatorView+AFNetworking
  * UIAlertView+AFNetworking
  * UIButton+AFNetworking
  * UIImageView+AFNetworking
  * UIProgressView+AFNetworking
  * UIRefreshControl+AFNetworking
  * UIWebView+AFNetworking


## Grand Central Dispatch
  - Dispatching Work Asynchronously to a Background Queue FB31
  - create a singleton FB33

```  
   +(instancetype)sharedInstance { 
     static dispatch_once_t once; 
     static id _sharedInstance = nil; 
     dispatch_once(&once, ^{
        _sharedInstance = [[self alloc] init]; 
     });
     return _sharedInstance; 
   }
```
   - NSOperation

￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼

## UITableView
* tableView IA53 / can be named anything
  * dataSource - set to the UIViewController and NOT the UITableView
  * delegate - set to the UIViewController and NOT the UITableView
* UITableViewDataSource:
  * cellForRowAtIndexPath IA56
    * dequeueReusableCellWithIdentifier
    * how to handle multiple different `types` here
       * UISearchBar
    * reloadData IA66
    * accessories in UITableViews
* custom UITableViewCells
  * updateCell model


7.25 UICollectionView

## User Interface text field, button IA59  

## TweetBook / Accounts Framework IA180
   ACAccountStore IA182
     ACAccountType IA182
     ACAccount IA182
       accountType
       credential
       identifier
       username
   - CredentialStore -   
   
## UICollectionView
## Autolayout
  - the status bar and your content IT256
  - text instead of icons IT260
  - make way for the content IT261
  Using Auto Layout for easier layout IT265
    - think constraints, not frames IT267
    - enabling AutLayout IT268
    - Scrolling the Scrolls IT269
    - Table Views and Auto Layout IT277
10. UIImage
11. UIText
   Text Kit  http://robots.thoughtbot.com/ios-text-kit-basics
     - text kit architecture IT144
     - dynamic type IT145
     - Letterpress Effects IT151
     - Exclusion Paths IT153
     - Dynamic Text Formatting and Storage IT155
        - Subclassing NSTextStorage
      NSTextStorage, NSLayoutManager, NSTextContainer  
12. UIKitDynamics
13. NSAttributedString
14. UIButton
15. LoggingIn
16. UIMapKit
17. Custom Transitions
   - animateTransition IT112
   - transitionDelegate IT113

  4 things
  1. custom transition
  2. custom dismissal
    2.5. using other animation techniques; UIView screenshot, Keyframe animation
  3. Navigation Controller Transitions
  4. Interactive Transitions

  9 steps: IT117

  3 protocols:
    1. UIViewControllerTransitionDelegate
    2. UIViewControllerAnimatedTransitioning
    3. UIViewControllerContextTransitioning


  - transition API IT115
  - transition process IT117
  - spicing up the transition IT118

  Navigation Controller Transitions IT128
   - adding a flip animation controller IT129
  Interactive Transitions
    - adding an interaction controller IT134
    - wiring it up IT138 

18. Container Controllers
  https://github.com/objcio/issue-12-custom-container-transitions
  and 
  git@github.com:cflesner/CLFContainerViewController.git
19. Page View Controllers

UIViewControllerAnimatedTransitioning,  transition context, This container view is where the animation actually takes place
20. Xcode 
   Standard / Assistant / Version
  Assistant Editor: command-option-return
  with Storyboard element selected, command-option-1 through 6
  Provisioning Profiles 

## Notifications
* SSL Certificate
* Keychain Access - Request Certificate from a Known Authority
* Must request Apple Push from Provisioning Profile
    - need a PEM file from P12
  http://joshsymonds.com/blog/2013/07/01/sidekiq-plus-houston-persistent-apple-connection-pooling/  
  http://joshsymonds.com/blog/2013/10/17/sidekiq-plus-houston-production-ready/
  Sidekiq integrates with ConnectionPool
  Sidekiq is ALL about workers
  do things restart in Sidekiq


## UIScrollView
  - contentSize

## UIPopoverController
  - primarily for iPad
  
## UIStoryboard, UIStoryboardSegue
   - can have multiple storyboards

## UIBezierPath
   - can clip to path

## CALayer - for border
## CLManager / MKMapView  
* how to get Latitude and Longitude

## Better Custom Drawing - PTL91    
 



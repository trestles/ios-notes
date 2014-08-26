Goal of this is to provide notes to someone who probably codes predominantly in something else but also does iOS work. I like starting with the simplest example to show a concept / pattern and hopefully be able to flesh it out.

IOS 7 in Action - IA
iOS 7 by Tutorials - IT
NSHipster Fake Book - FB
Apple Docs:
   View Controller Programming Guide - AVC

Programming iOS7 - P
iOS7 Programming Pushing the Limits - PTL   


1. rebuild iOS knowledge
Objective C - background: instance variables, methods, class methods
   - protocols IA54-5
      - specify in interface
      - methods would be required
      - to create a protocol

   - extensions - monkeypatching for Objective-C
MVC

26. Objective-C
  interface (.h) / implementation (.m)
    - in iterface file:
       public variables
       public methods (both instance and class)
       conforms to protocol information

    - in implementation file:   
      private variables
      method implementations


  calling methods:
    return type, named arguments

  id type
  casting

- blocks


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
     

     // from http://stackoverflow.com/questions/24961671/push-segues-can-only-be-used-by-uinavigationcontroller-error
     UINavigationController *recordNavigationController = (UINavigationController*)[self.storyboard instantiateViewControllerWithIdentifier:@"RecordNavigationController"];
     self presentViewController:recordNavigationController animated:YES completion:nil];

   maintain a reference to controller that displays and holds your tasks:
   @property (weak, nonatomic) id delegate; //IA61  and IA62
   connectiong controllers in storyboard - IA62
     - can be done only in context of Navigation Controller
   prepareForSegue IA64  

2.5.   
3. views - UIView, UIControl, UIResponder, 
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
5. AFNetworking and Networking

AFNetworking
   classes:
      NSURLConnection
        - AFHTTPRequestOperation
        - AFHTTPRequestOperationManager
        - AFURLConnectionOperation
      NSURLSession
        - AFHTTPSessionManager
        - AFURLSessionManager
      Reachability
        - AFNetworkReachabilityManager
      Security
        - AFSecurityPolicy
      Serialization
        - AFURLRRequestSerialization
        - AFURLResponseSerialization
      Support Files
      UIKit
        - AFNetworkActivityIndicatorManager
        - UIActivityIndicatorView+AFNetworking
        - UIAlertView+AFNetworking
        - UIButton+AFNetworking
        - UIImageView+AFNetworking
        - UIProgressView+AFNetworking
        - UIRefreshControl+AFNetworking
        - UIWebView+AFNetworking
NSURLSession

6. Grand Central Dispatch
  - Dispatching Work Asynchronously to a Background Queue FB31
  - create a singleton FB33
   +(instancetype)sharedInstance { 
     static dispatch_once_t once; 
     static id _sharedInstance = nil; 
     dispatch_once(&once, ^{
        _sharedInstance = [[self alloc] init]; 
     });
     return _sharedInstance; 
   }

   - NSOperation

￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼

7. UITableView
    - tableView IA53 / can be named anything
    - dataSource - set to the UIViewController and NOT the UITableView
    - delegate - set to the UIViewController and NOT the UITableView
    UITableViewDataSource:
    - cellForRowAtIndexPath IA56
      - dequeueReusableCellWithIdentifier
      - how to handle multiple different `types` here
      - UISearchBar
    - reloadData IA66
   - accessories in UITableViews
   custom UITableViewCells
      - updateCell model


7.25 UICollectionView

7.5 User Interface text field, button IA59  
7.75. TweetBook / Accounts Framework IA180
   ACAccountStore IA182
     ACAccountType IA182
     ACAccount IA182
       accountType
       credential
       identifier
       username
   - CredentialStore -   
8. UICollectionView
9. Autolayout
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

20.5. Notifications
  SSL Certificate
  Keychain Access - Request Certificate from a Known Authority
  Must request Apple Push from Provisioning Profile
    - need a PEM file from P12
  http://joshsymonds.com/blog/2013/07/01/sidekiq-plus-houston-persistent-apple-connection-pooling/  
  http://joshsymonds.com/blog/2013/10/17/sidekiq-plus-houston-production-ready/
  Sidekiq integrates with ConnectionPool
  Sidekiq is ALL about workers
  do things restart in Sidekiq
21. UIScrollView
  - contentSize
22. UIPopoverController
  - primarily for iPad
23. UIStoryboard, UIStoryboardSegue
   - can have multiple storyboards
24. UIBezierPath
   - can clip to path
25. CALayer - for border
26. CLManager / MKMapView  
    * how to get Latitude and Longitude

27. Better Custom Drawing - PTL91    
 



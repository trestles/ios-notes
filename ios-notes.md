Goal of this is to provide notes to someone who probably codes predominantly in something else but also does iOS work. I like starting with the simplest example to show a concept / pattern and hopefully be able to flesh it out.

- IOS 7 in Action - IA  
- iOS 7 by Tutorials - IT  
- NSHipster Fake Book - FB  
- Core iOS Developer's Cookbook - CC
- Apple Docs:
   - View Controller Programming Guide - AVC

- Programming iOS7 - P  
- iOS7 Programming Fundamentals PF
- iOS7 Programming Pushing the Limits - PTL   
- iOS 6 Coobook IC

### iOS knowledge
- Objective C - background: instance variables, methods, class methods
   - protocols IA54-5
      - specify in interface
      - methods would be required
      - to create a protocol

   - extensions - monkeypatching for Objective-C
- MVC
- static methods are only run once



## Events
  - traditionally, events are created and captured at the level of UIViewController
     - can be be created in Storyboard or in code
     - in Storyboard, would need to drag from item to UIViewController
        - does NOT need to have IBAction public interface
     - 
  - selectors
     - example of repeatedly calling selector in IA
     - registering a selector
     - simplest selector example   


UIImage - iOS7 doesn't run on single pixels iPhones but does run on single pixel iPads


## Gesture Recognizers
* gesture recognizer P195
* built-in UIGestureRecognizer subclasses 
* subclassing Gesture Recognizers P203
* Touch Delivery P208
* Hit Testing P208
   * multiple touch enabled P209
   * exclusive touch P209
   
   "keep in mind that layers do not receive touches " P210
   
* hit-test munging P213
* now, you can attach a UISwipeGestureRecognizer to the UIWebView P214
* delaysTouchesBegan P215   

##AFNetworking and Networking

classes:

1. NSURLConnection - for previous versions!!!
  * AFHTTPRequestOperation
  * AFHTTPRequestOperationManager
  * AFURLConnectionOperation
* NSURLSession
  * AFHTTPSessionManager \- this is the one you use; subclass of AFURLSessionManager
    * baseURL
    * requestSerializer
    * responseSerializer
    * manager - 
    * initWithBaseURL
    * initWithBaseURL:sessionConfiguration
    * GET, HEAD, POST, POST, PUT, PATCH, DELETE
  * AFURLSessionManager
    * session
    * operationQueue
    * responseSerializer
    * securityPolicy
    * reachabilityManager
    * NSArray *tasks
    * NSArray *dataTasks
    * NSArray *uploadTasks
    * NSArray *downloadTasks
    * completionQueue
    * completionGroup
    * attemptsToRecreateUploadTasksForBackgroundSessions
    * Setting Session Delegate Callbacks                        
    * Setting Task Delegate Callbacks                            
    * Setting Data Task Delegate Callbacks                        
    * Setting Download Task Delegate Callbacks                        
    * notifications
      * AFNetworkingTaskDidResumeNotification
      * AFNetworkingTaskDidCompleteNotification
      * AFNetworkingTaskDidSuspendNotification
      * AFURLSessionDidInvalidateNotification
      * AFURLSessionDownloadTaskDidFailToMoveFileNotification
      * AFNetworkingTaskDidCompleteResponseDataKey
      * AFNetworkingTaskDidCompleteSerializedResponseKey
      * AFNetworkingTaskDidCompleteResponseSerializerKey
      * AFNetworkingTaskDidCompleteAssetPathKey
      * AFNetworkingTaskDidCompleteErrorKey
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

## User Interface text field, button IA59  
### Gestures and Touches CC1
  - Recipe: Adding s simple direct manipulation interface
  - Recipe: Adding Pan Gestuer Recognizers
  - Recipe: using multiple gesture recognizers simultaneously
  - Recipe: Constraining Movement CC14
  - Recipe: Testing Touches CC15
  - Recipe: Testing Against a Bitmap CC17
  - Recipe: Drawing Touches Onscreen CC20
  - Recipe: Dragging From a Scroll View CC37
  - Recipe: Live Touch Feedback CC40
  - Recipe: Adding Menus to Views CC45
  
### Building and Using Controls 
  - The *UIControl* Class CC49
  - Recipe: Building Buttons CC56
  - Recipe: Animating Button Responses CC60
  - Recipe: Subclassing UIControl CC72
  - Recipe: Building a Star Slider CC76
  - Recipe: Building a Touch Wheel CC79
  - Recipe: Building a Pull Control CC83
  - Recipe: Building a Custom Lock Control CC88
  - Recipe: Image Gallery Viewer CC93
  - Building Toolbars CC96
  
### Alerting the User 
  - Talking Directly to Your User Through Alerts CC101
  - Recipe: Using Blocks with Alerts CC105
  - Recipe: Modal Progress Overlays CC117
  - Recipe: Custom Modal Alert View CC119
  - Recipe: Basic Popovers CC124
  - Recipe: Local Notifications CC126    


## TweetBook / Accounts Framework IA180

- ACAccountStore IA182
  - ACAccountType IA182
  - ACAccount IA182
    - accountType
    - credential
    - identifier
    - username
- CredentialStore
   
## UICollectionView

* UICollectionViewLayoutAttributes P460  
  * adopts the UIDynamicItem protocol P470
* UICollectionViewCell P460  
  * has a highlighted property and a selected property P460  
* UICollectionReusableView P460  
* UICollectionReusableView P460  
* UICollectionViewLayout P460  
    two categories:  
      1. static attributes (P460)  
      2. dynamic attributes  (P461)  
* UICollectionViewFlowLayout (P461)  
    - scroll direction  
    - a sectionInset (the margins for a section)  
    - itemSize (along with a minimumInteritemSpacing and minimumLineSpacing)  
    - headerReferenceSize  
    - footerReferenceSize  
* UICollectionViewDelegateFlowLayout protocol (P461)       
 
##### Using a Collection View (P462)
##### Custom Collection View Layouts (P465)

* layoutAtrributesForItemAtIndexPath: which returns a single 
* UICollectionViewLayoutAttributes
   * examples from WWDC P467
   * Switching Layouts (P469)
  

## Autolayout
  - the status bar and your content IT256
  - text instead of icons IT260
  - make way for the content IT261
  Using Auto Layout for easier layout IT265
    - think constraints, not frames IT267
    - enabling AutLayout IT268
    - Scrolling the Scrolls IT269
    - Table Views and Auto Layout IT277
    
## UIImage
  - imageNamed forces caching, CATileLayer 
  
## UIText
* Text Kit  http://robots.thoughtbot.com/ios-text-kit-basics
* text kit architecture IT144
* dynamic type IT145
* Letterpress Effects IT151
* Exclusion Paths IT153
* Dynamic Text Formatting and Storage IT155
  * Subclassing NSTextStorage
* NSTextStorage, NSLayoutManager, NSTextContainer  
      
## UIKitDynamics P174
* UIPushBehavior P175
* UICollisionBehavior P176
* UIDynamicItemBehavior P176
* UIDynamicAnimator P178
   * delegate
   * running 
   * elapsedTime 
   * updateItemsUsingCurrentState
   
  

## NSAttributedString

## UIButton

##LoggingIn
* see my example 
  
## UIMapKit


## Custom Transitions
   - animateTransition IT112
   - transitionDelegate IT113

##### 4 things
  1. custom transition
  2. custom dismissal
  3. using other animation techniques
    - UIView screenshot
    - Keyframe animation
  4. Navigation Controller Transitions
  5. Interactive Transitions

  9 steps: IT117

##### 3 protocols:
  1. UIViewControllerTransitionDelegate
  - UIViewControllerAnimatedTransitioning
  - UIViewControllerContextTransitioning


##### transitions
  - transition API IT115
  - transition process IT117
  - spicing up the transition IT118

##### Navigation Controller Transitions IT128
  - adding a flip animation controller IT129
   
##### Interactive Transitions
   - adding an interaction controller IT134
   - wiring it up IT138 

## Container Controllers
  https://github.com/objcio/issue-12-custom-container-transitions
  and 
  git@github.com:cflesner/CLFContainerViewController.git
  
## Page View Controllers
UIPageViewController P310 
assign a dataSource 
setViewControllers P310
can have a UIPageViewControllerDelegate


???UIViewControllerAnimatedTransitioning,  transition context, This container view is where the animation actually takes place

## Xcode 
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
  - alwaysBounceHorizontal
  - alwaysBounceVertical
  - bounces
  - bouncesZoom
  - canCancelContentTouches
  - contentInset
  - contentOffset
  - contentSize
  - decellerating
  - decelleratingRate

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
 



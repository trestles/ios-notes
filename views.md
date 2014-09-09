
##views - UIView, UIControl, UIResponder, 


   subviews, setNeedsDisplay

  * basis of what you see AND interactions P3
    * view hierarchy P3

UIView 

* alpha
* autoresizeSubviews
* autoresizeMask
* backgroundColor
* bounds
* center
* clearsContextBeforeDrawing
* clipToBounds
* contentMode
* contentScaleFactor
* exclusiveTouch
* frame
* gestureRecognizers
* hidden
* layer
* motionEffects
* multipleTouchEnabled
* opaque
* restorationIdentifier
* subviews
* superview
* tag
* tintAdjustmentMode
* tintColor
* transform
* userInteractionEnabled

UIResponder
Properties:

* inputAccessoryView
* inputView
* keyCommands
* textInputContextIdentifier
* textInputMode
* undoManager

##### UIWindow
various ways to get at UIWindow P6

###### Subview and Superview
* very flexible of overlapping and where things fit P7
* clipping, set in clipToBounds property P9
* a superview owns its subviews in the memory management sense much as an NSArray owns its elements P10

* superview / subviews P10; subviews are indexed starting at 0
* referring to other views - isDescendentOfView, viewWithTag, numeric tag (tag property)
  * addSubView, removeFromSuperview P10
   
* methods that you can override: P10
   1. didAddSubview / willRemoveSubview
   2. didMoveToSuperview / willMoveToSuperview
   3. didMoveToWindow / willMoveToWindow


##### Visibility and Opacity
  * set hidden to YES / NO P11
  * a hidden view does not normally recieve touch events P11
    
 center P15
 changing a view's bounds does not change its center; changing a views center does not change its bounds
 
#### CGAffineTransform P16

##### Graphics Context P58

##### Keyframe Animation P134

  * X,Y coordinates
  * initWithFrame

  * representing pixels
  * capturing events
     - where are actions defined?
     - can handle events in a UIViewController OR in UIView subclasses

  - UIView will delegate much of functionality to Core Animation specifically CALayer
  - CALayer doesn't handle user interaction
  - Each UIview has a `layer` property that is an instance of CALayer (known as the backing layer)
  - UIView is simply a wrapper, providing iOS specific funtionality such as touch handling and high-level interfaces for some of Core Animations low-level functionality
  - "For simple purposes, we don't really need to deal directly"
      - "CALayer has a `contents` property" but must be CGImage"
      - "Core Foundation types behave like Cocoa objects at runtime - known as toll-free-bridging"


## UIBezierPath
   - can clip to path

## CALayer - for border

## Better Custom Drawing - PTL91   


## UIKitDynamics P174
* UIPushBehavior P175
* UICollisionBehavior P176
* UIDynamicItemBehavior P176
* UIDynamicAnimator P178
   * delegate
   * running 
   * elapsedTime 
   * updateItemsUsingCurrentState
   
 


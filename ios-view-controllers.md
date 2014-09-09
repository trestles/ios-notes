

UIViewController

## ViewControllers
* instantiating VCs
     - initWithCoder
     - initWithNibName - why?

* UIViewController - lifecycle P329
  - Instantiating a Storyboard’s View Controller Programmatically AVC
  - Segues Automatically Instantiate the Destination View Controller AVC
    - where in the VC lifecycle?
  - Transitioning to a New Storyboard Requires a Programmatic Approach AVC
  - Displaying a View Controller’s Contents Programmatically AVC
  - how to show:
    - Make the view controller the root view controller of a window
    - Make it a child of a visible container view controller
    - Present it from another visible view controller
    - Present it using a popover (iPad only)
  - Anatomy of a Content View Controller AVC
  - Inititalizing A View Controller
    - Initializing a View Controller Loaded from a Storyboard  
    - Initializing View Controllers Programmatically
  - Managing Memory Efficiently AVC
  - Responding to Display-Related Notifications AVC
    - Determining Why a View’s Appearance Changed
  - Using View Controllers in the Responder Chain AVC  
  - Creating Custom Seques AVC
             
- UINavigationController - embed in
  - UINavigationItem
  - UITabBarItem, UIBarButtonItem
     
```
     // from http://stackoverflow.com/questions/24961671/push-segues-can-only-be-used-by-uinavigationcontroller-error
     UINavigationController *recordNavigationController = (UINavigationController*)[self.storyboard instantiateViewControllerWithIdentifier:@"RecordNavigationController"];
     self presentViewController:recordNavigationController animated:YES completion:nil];
```

- maintain a reference to controller that displays and holds your tasks:

```
   @property (weak, nonatomic) id delegate; //IA61  and IA62
```   
   * connectiong controllers in storyboard - IA62
     - can be done only in context of Navigation Controller
   * prepareForSegue IA64  


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
   

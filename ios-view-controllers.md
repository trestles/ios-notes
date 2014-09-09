

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

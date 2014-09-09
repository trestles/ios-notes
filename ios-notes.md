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

## TweetBook / Accounts Framework IA180

- ACAccountStore IA182
  - ACAccountType IA182
  - ACAccount IA182
    - accountType
    - credential
    - identifier
    - username
- CredentialStore
   
  

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
 



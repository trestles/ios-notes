
Networking

AFNetworking


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

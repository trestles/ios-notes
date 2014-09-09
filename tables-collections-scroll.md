


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


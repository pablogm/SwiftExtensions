# Useful Swift Extensions 

------

### String utils <a target="_blank" href="https://gist.github.com/pablogm/4ad14e100416d6a804aa">String+Utils.swift</a>
============

###### Localized string

```swift
"connect".localized
```

<sub>The "connect" string should be in your *Localizable.strings* files</sub>

###### Display an html string (i.e. html string to attributed string)

```swift
let attStringLeft = "<b><font face=\"HelveticaNeue\" size=\"6\" color=\"white\">\(speed)</font></b></br><font face=\"HelveticaNeue\" size=\"2\" color=\"white\">SPEED</font>".html2AttStr
```

###### Check if an email is valid

```swift
 guard emailTextField.text!.isValidEmail() else {
    return false
 }
```

###### Clean string

```swift
private func cleanupForm() {
    emailTextField.text?.clean()
    passwordTextField.text?.clean()
}
```

###### Generate random sring

```swift
let password = String.randomStringWithLength(16)
```

------

### Get UIColor from it hex representation  <a target="_blank" href="https://gist.github.com/pablogm/206fe8e4ae04b8fdb062">UIColor+Hex.swift</a>
============

E.g.

```swift
let color1 = UIColor(hex: 0x0000ff)
```

------


### Add some methods to the NSThread class to run a block on any thread you have a reference to. <a target="_blank" href="https://gist.github.com/pablogm/d20120a97912fea44bed">NSThread+blocks.swift</a>
============

E.g.

```swift
NSThread.performBlockOnMainThread({ () -> Void in

    // Code you want to execute on main thread            
            
})
```

------

### NSDate utils. <a target="_blank" href="https://gist.github.com/pablogm/b18618fa1e33b441fa98">NSDate+Utils.swift</a>
============

###### Get date by adding / subtracting days from now

```swift
let tenDaysAgo = NSDate.dateBySubstractingDays(10)
```

###### Get date at midnight

```swift
let midNight    = NSDate.dateAtPrevMidnight()
```

------

### UIViewController Utils. <a target="_blank" href="https://gist.github.com/pablogm/8906e68d950747888343">UIViewController+Utils.swift</a>
============

###### Custom status bar background color on UIViewController

*Option 1*:

Method Swizzling - Use customViewDidLoad instead of viewDidLoad
```swift
    // MARK: ViewController lifecycle
    
    override func customViewDidLoad() {
        
        super.customViewDidLoad()
    }
```

*Option 2*:

Call statusBarBackgroundColor(color: Int) on viewDidLoad() or viewWillAppear(animated: Bool)

```swift
    // MARK: ViewController lifecycle
    
    override func viewDidLoad() {
        super.viewDidLoad()
        statusBarBackgroundColor(0x0b6e99)
    }
```

###### Popup alert from UIViewController

*Simple alert*

```swift
@IBAction func UserEventsButtonTap() {
        
        dispatch_async(dispatch_get_main_queue()) {
            self.presentDefaultAlert("My Title", subText: "My Text", dismissText: "Ok")
        }
    }
```

*Complex alert: Implementing alert actions*

```swift
self.showAlert("My Title", message: "My Text", ok: "Ok", cancel: "Cancel",
    cancelAction: { (action) in
        print("Cancel action button pressed.")
    }, okAction: { (action) in
        print("Ok action button pressed.")
    }, completion: { () in
        print("Alert displayed.")
})
```

------

### Get top view controller  <a target="_blank" href="https://gist.github.com/pablogm/d4cb926fe419687a8fc5">UIApplication+Utils.swift</a>
============

E.g.

```swift
if let topController = UIApplication.topViewController() {
                            
    if topController is MyViewController {
                                
        dispatch_async(dispatch_get_main_queue()) {
                                    
                self?.performSegueWithIdentifier("MySegueId", sender: nil)
        }
    }
 }
```

------

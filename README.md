# Useful Swift Extensions 

### Localizing text <a target="_blank" href="https://gist.github.com/pablogm/4ad14e100416d6a804aa">String+Utils.swift</a>

E.g. *Localized string*

```
"connect".localized
```

The "connect" string should be in your *Localizable.strings* files

E.g. *Html to attributed string*

```
let attStringLeft = "<b><font face=\"HelveticaNeue\" size=\"6\" color=\"white\">\(speed)</font></b></br><font face=\"HelveticaNeue\" size=\"2\" color=\"white\">SPEED</font>".html2AttStr
```

E.g. *Check if an email is valid*

```
 guard emailTextField.text!.isValidEmail() else {
    return false
 }
```

E.g. *Clean string*

```
private func cleanupForm() {
    emailTextField.text?.clean()
    passwordTextField.text?.clean()
}
```

E.g. *Generate random sring*

```
let password = String.randomStringWithLength(16)
``


### Get UIColor from it hex representation  <a target="_blank" href="https://gist.github.com/pablogm/206fe8e4ae04b8fdb062">UIColor+Hex.swift</a>

E.g.

```
let color1 = UIColor(hex: 0x0000ff)
```

### Display an html string (i.e. html string to attributed string)   <a target="_blank" href="https://gist.github.com/pablogm/6d55c4ab921964aa508f">String+AttributedString.swift</a>

E.g.

```
"<b>Name:</b><br/>\(name)".html2AttStr
```

### Add some methods to the NSThread class to run a block on any thread you have a reference to. <a target="_blank" href="https://gist.github.com/pablogm/d20120a97912fea44bed">NSThread+blocks.swift</a>

E.g.

```
NSThread.performBlockOnMainThread({ () -> Void in

    // Code you want to execute on main thread            
            
})
```

### NSDate utils. <a target="_blank" href="https://gist.github.com/pablogm/b18618fa1e33b441fa98">NSDate+Utils.swift</a>

E.g. *Get date by adding / subtracting days from now*

```
let tenDaysAgo = NSDate.dateBySubstractingDays(10)
```

E.g. *Get date at midnight*

```
let midNight    = NSDate.dateAtPrevMidnight()
```

### UIViewController Utils. <a target="_blank" href="https://gist.github.com/pablogm/8906e68d950747888343">UIViewController+Utils.swift</a>

#### Custom status bar background color on UIViewController

E.g.

*Option 1*:

Method Swizzling - Use customViewDidLoad instead of built in viewDidLoad
```
    // MARK: ViewController lifecycle
    
    override func customViewDidLoad() {
        
        super.customViewDidLoad()
    }
```

*Option 2*:

Call statusBarBackgroundColor(color: Int) on viewDidLoad() or viewWillAppear(animated: Bool) for example

```
    // MARK: ViewController lifecycle
    
    override func viewDidLoad() {
        super.viewDidLoad()
        statusBarBackgroundColor(0x0b6e99)
    }
```

#### Popup alert from UIViewController

E.g. *Simple alert*

```
@IBAction func UserEventsButtonTap() {
        
        dispatch_async(dispatch_get_main_queue()) {
            self.presentDefaultAlert("My Title", subText: "My Text", dismissText: "Ok")
        }
    }
```

E.g. *Complex alert: Implementing alert actions*

```
self.showAlert("My Title", message: "My Text", ok: "Ok", cancel: "Cancel",
    cancelAction: { (action) in
        print("Cancel action button pressed.")
    }, okAction: { (action) in
        print("Ok action button pressed.")
    }, completion: { () in
        print("Alert displayed.")
})
```

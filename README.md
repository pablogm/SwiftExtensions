# Useful Swift Extensions 

### Localizing text <a target="_blank" href="https://gist.github.com/pablogm/4ad14e100416d6a804aa">String+Localizable.swift</a>

E.g.

```
"connect".localized
```

The "connect" string should be in your *Localizable.strings* files

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

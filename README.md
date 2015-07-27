### Mixpanel-Swift ###

[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)

Swift wrapper framework for MixPanel with Carthage support.

### How does it work ? ###

This projects wraps the [mixpanel-iphone](https://github.com/mixpanel/mixpanel-iphone) as a Swift framework and makes it Carthage compatible. To achieve this, it adds the source from [mixpanel-iphone](https://github.com/mixpanel/mixpanel-iphone) as a git subtree module in to the folder *mixpanel-src*. This makes it easier to update the source in the future with the command ```git subtree pull```.

### Installation ###

Add ```github "hemantasapkota/mixpanel-swift"``` to your ```Cartfile``` and execute ```carthage update```. This builds the **MixPanelWrapper.framework** file. Add this to the **Embedded Binaries** section on XCode.

### Usage ###

In your *AppDelegate.swift*

```
import MixPanelWrapper

func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject : AnyObject]?) -> Bool {

    // mixpanelToken is a constant set somewhere in your project
    MixPanelWrapper.Mixpanel.sharedInstanceWithToken(mixpanelToken)
    
    MixPanelWrapper.Mixpanel.sharedInstance().track("Dev App Launch", properties: [
        "Hello" : "World"
    ])

}
```

The setup is done.

### Licence ###

The MIT License (MIT)

Copyright (c) 2015 Hemanta Sapkota

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

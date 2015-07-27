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

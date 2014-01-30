PPEnterpriseBuildService
========================

Simple class that detects newer available versions of an enterprise-distributted app by scanning it's plist file.


##How it Works

### Get the Source Code

Preferred way of integrating PPEnterpriseBuildService is to use CocoaPods. Just add following line to the Podfile of your project.

```ruby
pod 'PPEnterpriseBuildService', :git => 'https://github.com/petrpavlik/PPEnterpriseBuildService.git'
```

### Implement it

Import *PPEnterpriseBuildService.h* and put following piece of code in *application:didFinishLaunchingWithOptions:*.

```Objective-C
[[PPEnterpriseBuildService 
   sharedInstanceWithPlistURL:[NSURL URLWithString:@"https://example.com/your-enterprise-app/app.plist"] 
   installURL:[NSURL URLWithString:@"https://example.com/your-enterprise-app"]] 
   startDetectingNewVersions];
```

PPEnterpriseBuildService will try to detect new version on app's startup and each time it goes foreground. You can implement EnterpriseBuildServiceDelegate if you wish to be notified when detection fails.

![alt text](https://photos-4.dropbox.com/t/0/AADFVWlTpsxUoebUSEBBgeTFRpNZl1H14PI_8bVzdGGrnA/12/4175299/png/2048x1536/3/1391097600/0/2/Screenshot%202014-01-30%2015.08.41.png/M0NqBaaIXHd5mm2C9T6zb6bV_mZFrQLt8-wCrv9km5Y "Magic here")




PPEnterpriseBuildService
========================

Simple class that detects newer available versions of an enterprise-distributted app by scanning it's plist file.


##How it Works

Put following piece of code *application:didFinishLaunchingWithOptions:*.

```Objective-C
[[PPEnterpriseBuildService sharedInstanceWithPlistURL:[NSURL URLWithString:@"https://example.com/your-enterprise-app/app.plist"] installURL:[NSURL URLWithString:@"https://example.com/your-enterprise-app"]] startDetectingNewVersions];
```

PPEnterpriseBuildService will try to detect new version on app's startup and each time it goes foreground. You can implement EnterpriseBuildServiceDelegate if you wish to be notified when detection fails.



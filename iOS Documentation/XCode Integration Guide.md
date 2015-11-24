# XCode Integration Guide
## Manual Integration:
**Step #1**

Open XCode and click on new project from file menu Choose your application type: single view application and click next:

![enter image description here](https://code.oovoo.com/native/docs/ios/NewProject/1.png)

**Step #2**

Choose your application name and click next:

![enter image description here](https://code.oovoo.com/native/docs/ios/NewProject/2.png)

**Step #3**

Choose project location on local disk and click create project:

![enter image description here](https://code.oovoo.com/native/docs/ios/NewProject/3.png)

**Step #4**

Select application target and focus on build phases tab and than click on + add frameworks and libraries:

![enter image description here](https://code.oovoo.com/native/docs/ios/NewProject/4.png)

**Step #5**

Choose ooVoo SDK framework file and click open:

![enter image description here](https://code.oovoo.com/native/docs/ios/NewProject/5.png)

**Step #6** Add additional frameworks required by ooVoo SDK:

```objective-c
 - UIKit.framework in Frameworks
 - CFNetwork.framework
 - CoreMedia.framework
 - CoreLocation.framework
 - QuartzCore.framework
 - OpenGLES.framework
 - AudioToolbox.framework
 - CoreAudio.framework
 - AVFoundation.framework
 - CoreVideo.framework
 - SystemConfiguration.framework
 - VideoToolbox.framework
 - CoreGraphics.framework
 - libc++.1.dylib
 - MediaPlayer.framework
 - Accelerate.framework
 - libstdc++.6.0.9.dylib
 - libc.dylib
 - MobileCoreServices.framework
 - QuickLook.framework
 - AssetsLibrary.framework
 - libz.1.1.3.dylib
```

![enter image description here](https://code.oovoo.com/native/docs/ios/NewProject/6.png)

**Step #7**

Open `ViewController.h` file and add property `ooVooClient`:

```objective-c
    //  ViewController.h

    //  MyOoVooVideoApp

    //

    //  Created by XXX on 6/5/15.

    //  Copyright (c) 2015 XXX. All rights reserved.

    //

    import <UIKit/UIKit.h>
    // Import for the library in the ooVooSDK ( The framework you have just added )
    import "ooVooSDK/ooVooSDK.h"
    @interface ViewController : UIViewController
    @property (retain, nonatomic) ooVooClient *sdk; // Make an instance of the ooVooClient sdk And ENJOY ....
    @end
```

![enter image description here](https://code.oovoo.com/native/docs/ios/NewProject/7.png)

**Step #8**

 Add the following piece of code:

```objective-c
    //  ViewController.m

    //  MyOoVooVideoApp
    //
    //  Created by xxx on 6/5/15.

    //  Copyright (c) 2015 XXX. All rights reserved.
    //



     import "ViewController.h"

        @interface ViewController ()

        @end

        @implementation ViewController

        - (void)viewDidLoad {
            [super viewDidLoad];

        // Only 3 steps
        // 1. Create authorization

        self.sdk = [ooVooClient sharedInstance];

        // Set The app token for an app you create


  define ApplicationToken @"Your Application Token"

        // Call for authorizeClient to confirm your App Token

        [self.sdk authorizeClient:ApplicationToken
                       completion:^(SdkResult *result) {
                           if (result.Result == sdk_error_OK)
                           {
                               NSLog(@"Good Authorization");
                               [self login];
                           }
                           else
                           {
                               NSLog(@"Failed Authorization - Check your token !");

                           }
                       }];



     }

    //  2 . login user ....
    -(void)login{

        [self.sdk.Account login:@"UserName"
                     completion:^(SdkResult *result) {
                         if (result.Result == sdk_error_OK)
                         {
                             NSLog(@"Login Success");
                             [self createPanel];
                         }
                         else
                         {
                             UIAlertView *alert =[[UIAlertView alloc] initWithTitle:@"Login Error" message:result.description delegate:nil cancelButtonTitle:@"Ok" otherButtonTitles:nil, nil];
                             [alert show];
                         }
                     }];
    }
    // 3. Create a video panel and open camera
    -(void)createPanel{

        VideoPanel *panel = [[VideoPanel alloc]initWithFrame:self.view.frame];
         [self.view addSubview:panel];
        [self.sdk.AVChat.VideoController bindVideoRender:nil/*[ActiveUserManager activeUser].userId*/ render:panel];
        [self.sdk.AVChat.VideoController openCamera];

    }
    - (void)didReceiveMemoryWarning {
        [super didReceiveMemoryWarning];
        // Dispose of any resources that can be recreated.
    }
    @end
```

 Compile and run your project:

![enter image description here](https://code.oovoo.com/native/docs/ios/NewProject/8.png)

## Integration using Cocoapods
To have the SDK integrated into your project using Cocoapods just insert the following into your Podfile:

```ruby
pod ‘ooVooSDK-iOS’, ~>‘2.0’
```

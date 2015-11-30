# Swift Integration Guide

## Introduction
Swift is a multi-paradigm, compiled programming language created by Apple Inc. for iOS, OS X, and WatchOS development. Swift was introduced at Apple's 2014 Worldwide Developers Conference (WWDC).

This tutorial will introduce you to the basics of the ooVoo SDK and help to create a new project based on the Swift language.

## Creating a New project
**Step #1**
Open XCode and select `File`-> `New` -> `Project`

![](https://code.oovoo.com/native/docs/ios/swift/project_1.png)

**Step #2**
Choose `Application` -> `Single View Application` and click `Next`

![](https://code.oovoo.com/native/docs/ios/swift/project_2.png)

**Step #3**
In the window that opens input your Product Name, Organization Identifier and select `Swift` as the language.

![](https://code.oovoo.com/native/docs/ios/swift/project_3.png)

**Step #4**
After the project is created you must download and add the ooVoo SDK framework into the project. This can be done as follows:
* Click on the target of the project
* Select `Build Phases` from the top navigation bar
* Under `Link Binary with Libraries` click on the `+`

![](https://code.oovoo.com/native/docs/ios/swift/project_4.png)

* The "Choose frameworks and libraries to add" window will open, on the bottom of the windows select `Add Another`

![](https://code.oovoo.com/native/docs/ios/swift/project_5.png)

* Navigate to the folder where your ooVooSDK.framework file is and select it.

![](https://code.oovoo.com/native/docs/ios/swift/project_6.png)

* You must also add the following included frameworks (click on `+` to add them:
```objective-c
CoreMedia.framework
CoreTelephony.framework
VideoToolbox.framework
Accelerate.framework
AudioToolbox.framework
AVFoundation.framework
libc++.1.dylib
libz.dylib
```
![](https://code.oovoo.com/native/docs/ios/swift/project_7.png)

**Step #5**
You must also create a bridging header in order to bridge between the objective-c classes and the swift classes.

![](https://code.oovoo.com/native/docs/ios/swift/project_10.png)

* Right click on the target of the project and select `New File`

![](https://code.oovoo.com/native/docs/ios/swift/project_8.png)

* Choose `Header File` and click on `Next`

![](https://code.oovoo.com/native/docs/ios/swift/project_9.png)

* Name your file and click `Create`

* In your objective-c bridging header file, import evert objective-c header you want to expose to swift. For example:

![](https://code.oovoo.com/native/docs/ios/swift/project_11.png)

You are now ready to develop your project!

## Code Samples
Here we illustrate some sample code which show implementation of methods from the ooVoo SDK.

We cover the following methods:
* authorizeClient
* login
* join, leave (Once you press `Join` in the sample app, you should see the text change to `Leave`. This illustrates receiving a response from the server.)

### authorizeClient
This method authorizes access to ooVooClient SDK. This method is asynchronous, and an event will be raised on the main thread.

First you need to get the singleton reference to ooVooClient SDK:

```objective-c
self.sdk = ooVooClient.sharedInstance();
authorize();
```
Now you can call the `authorizeClient` method:

```objective-c
func authorize()
    {
        self.sdk.authorizeClient(Token, completion: { (result:SdkResult!) -> Void in


            var err :sdk_error!=result.Result;
            if (err==sdk_error.OK)
            {
	       NSLog("authorization ok");
               ………………..
            }
            else
            {
                NSLog("fail  autorization");
				       ………………..
            }


        	});
}
```

### login
This method allows you to perform a login with an existing user. If you have different views of the UI when you login again you should perform:

```objective-c
self.sdk = ooVooClient.sharedInstance();
```

And now you can call the `login` method:

```objective-c
self.sdk.Account.login(self.txt_UserId.text, completion: { (result:SdkResult!) -> Void in
if result.Result != sdk_error.OK
{
	NSLog("login ok");

}
else
{
	NSLog("login failed");

}

})
```

### join, leave
These methods allows you to join a video conference and to disconnecting from one.

First, you need to initialize following elements:

```objective-c
self.sdk = ooVooClient.sharedInstance();
authorize();
```
Now you can call the `authorizeClient` method:

```objective-c
func authorize()
    {
        self.sdk.authorizeClient(Token, completion: { (result:SdkResult!) -> Void in


            var err :sdk_error!=result.Result;
            if (err==sdk_error.OK)
            {
		NSLog("authorization ok");
		………………..
            }
            else
            {
                NSLog("fail  autorization");
				       ………………..
            }


        	});
}
```

If you have different views of the UI when you login again you should perform:

```objective-c
 import UIKit

class VideoConference: UIViewController,ooVooAVChatDelegate,ooVooVideoControllerDelegate{
    
    // declare objects and variable
    var sdk : ooVooClient!
    var isConnectedToVideoConference : Bool = false  // are we connected to video conference ?
    let videoPanel = ooVooVideoPanel()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        self.addVideoPanelOnView()
        initializeAVChat()
        addNavigationRightButton()
    }
    
    override func viewWillAppear(animated: Bool) {
        self.navigationItem.title="Video Conference"
    }
    
    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }
    
    // add the ooVoo Videopanel View On Self.View
    func addVideoPanelOnView()
    {
        videoPanel.frame=self.view.frame
        self.view.addSubview(videoPanel)
    }
    
    // initialize Audio and Video sdk
    func initializeAVChat(){
        self.sdk = ooVooClient.sharedInstance()
        self.sdk.AVChat!.delegate=self;
        self.sdk.AVChat.VideoController.delegate = self;
        // viewPanel is an sdk view object for displaying the video
        // viewPanel can be allocated by code or with IBOutlet reference
        self.sdk.AVChat.VideoController.bindVideoRender(nil, render: videoPanel)
        self.sdk.AVChat.VideoController.openCamera() // -> will return  didCameraStateChange Delegate 
    }
    
    // create a join confference button on the navigation bar ( right button )
    func addNavigationRightButton(){
        let btn = UIBarButtonItem(title: "Join", style: .Plain, target: self, action: "actJoin")
        self.navigationItem.rightBarButtonItem=btn
    }
    
    // click on navigation bar right button
    func actJoin()
    {
        
        if (isConnectedToVideoConference == false)
        {
            self.navigationItem.rightBarButtonItem?.enabled=false;
            self.sdk.AVChat.join("ConferenceID", user_data: "DisplayName"); // connect conference
        }
        else
        {
            self.navigationItem.rightBarButtonItem?.enabled=false;
            self.sdk.AVChat.leave(); // disconnect conference
        }
    }
    
    
    // oovooAVChat Delegate
    
    func didParticipantJoin(participant: ooVooParticipant!, user_data: String!) {
        
    }
    
    func didParticipantLeave(participant: ooVooParticipant!) {
        
    }
    
    // after calling the join method in " func actJoin " this method return from the delegate
    func didConferenceStateChange(state: ooVooAVChatState, error code: sdk_error) {
        
        
        if(state.rawValue == ooVooAVChatState.Joined.rawValue && code.rawValue == sdk_error.OK.rawValue )
        { // connection success
            self.isConnectedToVideoConference=true
            self.navigationItem.rightBarButtonItem?.title = "Leave" ;
            self.navigationItem.rightBarButtonItem?.enabled=true;
        }
        else
        { // leave or connection fail for some reason
            self.isConnectedToVideoConference=false
            self.navigationItem.rightBarButtonItem?.title = "Join" ;
            self.navigationItem.rightBarButtonItem?.enabled=true;
        }
        
    }
    
    func didReceiveData(uid: String!, data: NSData!) {
        
    }
    
    func didConferenceError(code: sdk_error) {
        
    }
    
    func didNetworkReliabilityChange(score: NSNumber!) {
        
    }
    
    func didSecurityState(is_secure: Bool) {
        
    }
    
    
    // ooVooVideoControllerDelegate
    
    func didRemoteVideoStateChange(uid: String!, state: ooVooAVChatRemoteVideoState, width: Int32, height: Int32, error code: sdk_error) {
        
    }
    
    func didCameraStateChange(state: ooVooDeviceState, devId: String!, width: Int32, height: Int32, fps: Int32, error code: sdk_error) {
        
        if(state.rawValue == ooVooAVChatState.Joined.rawValue && code.rawValue == sdk_error.OK.rawValue )
        {
            // camera opened
        }
        else
        {
            // camera close or some error
        }
        
    }
    
    func didVideoTransmitStateChange(state: Bool, devId: String!, error code: sdk_error) {
    }
    
    func didVideoPreviewStateChange(state: Bool, devId: String!, error code: sdk_error) {
        
    }
    
}
```

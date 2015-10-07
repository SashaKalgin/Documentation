# Swift Integration Guide

<!-- TOC depth:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Swift Integration Guide](#swift-integration-guide)
- [Introduction](#introduction)
- [Creating a New project](#creating-a-new-project)
- [Code Samples](#code-samples)
	- [authorizeClient](#authorizeclient)
	- [login](#login)
	- [join, leave](#join-leave)
<!-- /TOC -->

# Introduction
Swift is a multi-paradigm, compiled programming language created by Apple Inc. for iOS, OS X, and WatchOS development. Swift was introduced at Apple's 2014 Worldwide Developers Conference (WWDC).

This tutorial will introduce you to the basics of the ooVoo SDK and help to create a new project based on the Swift language.

# Creating a New project
**Step #1** Open XCode and select `File`-> `New` -> `Project`

![](https://code.oovoo.com/native/docs/ios/swift/project_1.png)

**Step #2** Choose `Application` -> `Single View Application` and click `Next`

![](https://code.oovoo.com/native/docs/ios/swift/project_2.png)

**Step #3** In the window that opens input your Product Name, Organization Identifier and select `Swift` as the language.

![](https://code.oovoo.com/native/docs/ios/swift/project_3.png)

**Step #4** After the project is created you must download and add the ooVoo SDK framework into the project. This can be done as follows:
- Click on the target of the project
- Select `Build Phases` from the top navigation bar
- Under `Link Binary with Libraries` click on the `+`

![](https://code.oovoo.com/native/docs/ios/swift/project_4.png)
- The "Choose frameworks and libraries to add" window will open, on the bottom of the windows select `Add Another`

![](https://code.oovoo.com/native/docs/ios/swift/project_5.png)
- Navigate to the folder where your ooVooSDK.framework file is and select it.

![](https://code.oovoo.com/native/docs/ios/swift/project_6.png)
- You must also add the following included frameworks (click on `+` to add them:
- CoreMedia.framework
CoreTelephony.framework
VideoToolbox.framework
Accelerate.framework
AudioToolbox.framework
AVFoundation.framework
libc++.1.dylib
libz.dylib
- ![](https://code.oovoo.com/native/docs/ios/swift/project_7.png)

**Step #5** You must also create a bridging header in order to bridge between the objective-c classes and the swift classes.

![](https://code.oovoo.com/native/docs/ios/swift/project_10.png)
- Right click on the target of the project and select `New File`

![](https://code.oovoo.com/native/docs/ios/swift/project_8.png)
- Choose `Header File` and click on `Next`

![](https://code.oovoo.com/native/docs/ios/swift/project_9.png)
- Name your file and click `Create`
- In your objective-c bridging header file, import evert objective-c header you want to expose to swift. For example:

![](https://code.oovoo.com/native/docs/ios/swift/project_11.png)

You are now ready to develop your project!

# Code Samples
Here we illustrate some sample code which show implementation of methods from the ooVoo SDK.

We cover the following methods:
- authorizeClient
- login
- join, leave (Once you press `Join` in the sample app, you should see the text change to `Leave`. This illustrates receiving a response from the server.)

## authorizeClient
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

## login
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

## join, leave
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
  self.sdk = ooVooClient.sharedInstance()
  self.sdk.AVChat!.delegate=self;
  self.sdk.AVChat.VideoController.delegate = self;
  self.sdk.AVChat.VideoController.bindVideoRender(nil, render: viewPanel)
  self.sdk.AVChat.VideoController.openCamera()

  func actJoin(){

        if self.navigationItem.rightBarButtonItem?.title == "Join"
        {
            self.sdk.AVChat.join("ConferenceID", user_data: "DisplayName");
        }
        else
        {
            self.sdk.AVChat.leave();
        }
    }


    // oovooAVChat Delegate

    func didParticipantJoin(participant: ooVooParticipant!, user_data: String!) {

    }

    func didParticipantLeave(participant: ooVooParticipant!) {

    }

    func didConferenceStateChange(state: ooVooAVChatState, error code: sdk_error) {
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

    }

    func didVideoTransmitStateChange(state: Bool, devId: String!, error code: sdk_error) {

        self.navigationItem.rightBarButtonItem?.title = state ? "Leave" : "Join";

    }

    func didVideoPreviewStateChange(state: Bool, devId: String!, error code: sdk_error) {

    }
```

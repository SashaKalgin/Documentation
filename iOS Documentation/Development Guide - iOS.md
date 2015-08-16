# Developing With the iOS SDK
<!-- MarkdownTOC -->

- [What is included in the ooVoo Video Chat SDK for iOS download package?](#what-is-included-in-the-oovoo-video-chat-sdk-for-ios-download-package)
- [How do I setup the ooVoo SDK in my development environment?](#how-do-i-setup-the-oovoo-sdk-in-my-development-environment)
- [How do I setup the ooVoo SDK in my development environment using CocoaPods?](#how-do-i-setup-the-oovoo-sdk-in-my-development-environment-using-cocoapods)
- [How do I build and run the ooVoo sample app included in the SDK download package?](#how-do-i-build-and-run-the-oovoo-sample-app-included-in-the-sdk-download-package)
- [Developing With the iOS SDK](#developing-with-the-ios-sdk)
- [How do I connect my users in a video call?](#how-do-i-connect-my-users-in-a-video-call)
- [Before You Begin: Events and Notifications](#before-you-begin-events-and-notifications)
- [How do I initialize ooVoo SDK?](#how-do-i-initialize-oovoo-sdk)
- [How do I create/join a conference?](#how-do-i-createjoin-a-conference)
- [How can I init audio ?](#how-can-i-init-audio-)
- [How can I configure the audio mode (i.e. Enable audio only calls)?](#how-can-i-configure-the-audio-mode-ie-enable-audio-only-calls)
- [How do I use the VideoPanel object?](#how-do-i-use-the-videopanel-object)
- [How do I display my local preview video in my app?](#how-do-i-display-my-local-preview-video-in-my-app)
- [How do I start/stop sending my audio and video streams to a conference?](#how-do-i-startstop-sending-my-audio-and-video-streams-to-a-conference)
- [How do I start/stop receiving the video streams of remote participants in a conference?](#how-do-i-startstop-receiving-the-video-streams-of-remote-participants-in-a-conference)
- [How do I display a remote participant's video in my app?](#how-do-i-display-a-remote-participant's-video-in-my-app)
- [Can I control the layout of the video windows?](#can-i-control-the-layout-of-the-video-windows)
- [How do I play the audio of a conference?](#how-do-i-play-the-audio-of-a-conference)
- [How do I select from multiple cameras?](#how-do-i-select-from-multiple-cameras)
- [How do I set camera video for a call?](#how-do-i-set-camera-video-for-a-call)
- [How can I use video filters within my app?](#how-can-i-use-video-filters-within-my-app)
- [How can I send messages while in a call?](#how-can-i-send-messages-while-in-a-call)
- [What events fired during a conference should my app pay attention to?](#what-events-fired-during-a-conference-should-my-app-pay-attention-to)
- [How do I leave a conference?](#how-do-i-leave-a-conference)
- [How do I close a conference?](#how-do-i-close-a-conference)
- [How do I handle incoming phone calls during a conference?](#how-do-i-handle-incoming-phone-calls-during-a-conference)
- [How do I handle call security with my app?](#how-do-i-handle-call-security-with-my-app)
- [How do I check if specific resolution level supported by all devices in call?](#how-do-i-check-if-specific-resolution-level-supported-by-all-devices-in-call)
- [How do I check if specific resolution level supported by my device?](#how-do-i-check-if-specific-resolution-level-supported-by-my-device)
- [How do I change the output device for audio playback?](#how-do-i-change-the-output-device-for-audio-playback)

<!-- /MarkdownTOC -->


## What is included in the ooVoo Video Chat SDK for iOS download package?
The SDK package contains the following items: iOS SDK:
- docs - Developer Guide PDF (this doc)
- ooVooSDK.framework : the ooVoo SDK for iOS
  - headers : the ooVoo SDK header files with inline documentation
  - ooVooSDK-iOS: the ooVoo SDK library binary supporting armv7, arm64 and i386/x86_64 (for simulators) platforms

- ooVooSample: the complete source project bundle of a sample multi-party video chat application built with the ooVoo SDK.

 

## How do I setup the ooVoo SDK in my development environment?
Getting started with the ooVoo SDK for iOS is super simple. First, in XCode, create new iOS project or open an existing one. Then in your project right click on the "**Frameworks**" folder, select "**Add Files to** "**Project Name**"" and import "**ooVooSDK.framework**" into your source tree from the folder where you downloaded the SDK.

![enter image description here](https://code.oovoo.com/native/docs/ios/1_getting%20started.png)

![enter image description here](https://code.oovoo.com/native/docs/ios/2_getting%20started.png)

In your source code add

```objective-c
    #import <ooVooSDK/ooVooSDK.h>
```

Do not forget to import additional frameworks used by ooVooSDK and provided by XCode:

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

**That's it!** Now you are ready to call methods and receive events from the ooVoo SDK for iOS. 

## How do I setup the ooVoo SDK in my development environment using CocoaPods?
Just add following line to your Podfile:

```objective-c
    pod ‘ooVooSDK2’, ~>‘2.0’
```

## How do I build and run the ooVoo sample app included in the SDK download package?
First, navigate to where you've saved the downloaded SDK file and open the "**ooVooSample**" folder then double click the "**ooVooSample**" project file to open it in XCode.

![enter image description here](https://code.oovoo.com/native/docs/ios/3_sample_2.png)

Build it for your simulator or your connected device and run it.

![enter image description here](https://code.oovoo.com/native/docs/ios/4_xcode.png)

To authenticate, you can either pre-populate the `LoginParameters.h` file with your credentials or insert them in the app settings.

![enter image description here](https://code.oovoo.com/native/docs/ios/ios_sample/10.png)

•    **"App Token"** – Created by you for your App in the developer portal. Pay special attention when pasting this as there are often copy/paste issues.

Now go back to your home page and run the app. Fill in your user ID and click login:

![enter image description here](https://code.oovoo.com/native/docs/ios/ios_sample/6.jpg)

Fill in your conference ID and Display name:

![enter image description here](https://code.oovoo.com/native/docs/ios/ios_sample/7.jpg)

•    **"Conference ID"** – the name of the ooVoo video conference you want to join. If this is a new name under a specific Application ID a new conference will be created and you will be the first participant in the conference. To have other "ooVooSample" app users to join the conference, simply have them enter the same Conference ID string.

Hit the **"Join"** button and enjoy!

![enter image description here](https://code.oovoo.com/native/docs/ios/ios_sample/8.jpg)

## Developing With the iOS SDK
> Note: Check out our new developer portal and dashboard at [http://developer.oovoo.com](http://developer.oovoo.com). There you can generate AppIDs, tokens and track usage statistics. **Beginning v2.0, existing AppIDs created prior to v2.0, that now wish to upgrade to v2.0, must generate a new token in the dashboard for use with the new version of the SDK.**

## How do I connect my users in a video call?
In ooVoo a video call is named as _"conference"_. Each conference is identified by a unique _"Conference ID"_. To connect two or more users of your application in a video call, you simply put those users in the same ooVoo conference by having them joining conference using the same Conference ID. It should be noted that ooVoo SDK does not handle the "signaling" steps per se between the end users of your application. It is up to you the developer to manage the distribution of the corresponding Conference ID to the target end user(s) by your own application logic.

## Before You Begin: Events and Notifications
The ooVoo SDK uses completion block extensively to notify your application to just about everything that is happening when exercising the functionalities provided by the SDK. For some of asyncronous events it is not possible so we provide you with protocols you need to implement and register with ooVoo SDK so it can notify you.

```objective-c
self.sdk.AVChat.delegate = self;
self.sdk.Account.delegate = self;
```

## How do I initialize ooVoo SDK?
In order to initialize SDK you need to authorize your application token first:

```objective-c
    [[ooVooClient sharedInstance] authorizeClient:TOKEN
        completion:^(SdkResult* result) {
                 // Login into ooVoo service
                 ...
    }];
```

Then you need to login into ooVoo service with a participantId so that ooVoo's service can provide you with a unique session token. This token is hidden from you and not accesible but without it no other operation which requires usage of backend services will not work.

```objective-c
    [[ooVooClient sharedInstance].Account login: participantId.text
         completion:^(SdkResult * result) {
           NSLog(@"result code=%d result description %@", result.Result, result.description);

           if (result.Result)
                // Logged in, now can make a call
                ...
    }];
```

## How do I create/join a conference?
Technically, there is no difference between being the first to join a conference (creating it) and being second or third (joining an existing conference). The ooVoo Video Platform handles all backend setup and makes it transparent to the user.

All you need to do is to provide the same _Conference ID_ to all clients that you want to join the same conference. If the Conference ID already exists, the user will be added to the existing conference identified by the Conference ID and your app will receive a notification from the SDK indicating if the join conference action was successful.

If the Conference ID doesn't exist yet, a new conference will be created by the ooVoo video cloud service. If the Conference ID already exists, the user will be added to the existing conference identified by the Conference ID.

Your app will be called on `didConferenceStateChange` in `ooVooAVChatDelegate` protocol from the SDK indicating if the join conference action was successful.

```objective-c
    -(void)didConferenceStateChange:(ooVooAVChatState)state error:(sdk_error)code {
        [self showAndRunSpinner:NO];

        NSLog(@"state %d code %d", state, code);

        if (state == ooVooAVChatStateJoined && code == sdk_error_OK) {
          ...
        } else {
          ...
        }
    }
```

If the join is successful, your application will be called with `didParticipantJoin` in `ooVooAVChatDelegate` protocol when other participants join the conference.

```objective-c
    - (void)didParticipantJoin:(id<ooVooParticipant>)participant user_data:(NSString* )user_data;
    {

    }
```

Other participants in the conference will also get notified that a new user, identified by a unique Participant ID assigned by ooVoo to represent your identity in the conference, has joined.

## How can I init audio ?

```objective-c
    self.sdk.AVChat.AudioController initAudio:^(ooVooSdkResult init_Audio_result){
        if(init_Audio_result.result == sdk_error.OK)
        {
            // Audio inited
        }
        else
        {
            // An error happened
        }
    }};
```

If audio was inited successful the means that audio capture and playback activated on the device and you will see a red panel on top of device if your application goes to background.

## How can I configure the audio mode (i.e. Enable audio only calls)?
   General difference between voice only and video chat mode are initial audio route direction.    For audio only conference the audio route on start set to earpice or one from headphones or bluetooth if the accessories    are connected to device. For video chat mode the initial audio route set to speakers or one from headphones or bluetooth     if the accessories are connected to the device.

```objective-c
   [sdk.AVChat.AudioController setConfig:OOVOOAudioModeVoiceChat forKey:ooVooAudioControllerConfigKeyAudioSetMode];
```

## How do I use the VideoPanel object?
  The `VideoPanel` object is our implementation for rendering a video stream for a participant, it is subclass of `UIView`.   You can construct your own look and feel for by inheritance or aggregation of the object.

## How do I display my local preview video in my app?
There are separate API calls to turn the camera on/off, for preview control and video transmission. See below. In order to display preview you must turn on camera first.

```objective-c
    @property (retain, nonatomic) ooVooClient* sdk;
    self.sdk = [ooVooClient sharedInstance];
    [self.sdk.AVChat.VideoController openCamera];
```

Once you receive the proper notification that the camera has started (see diagram below) you can now call:

```objective-c
    -(void)didCameraStateChange:(BOOL)state devId:(NSString* )devId width:(const int)width height:(const int)height fps:(const int)fps error:(sdk_error)code {
        NSLog(@"didCameraStateChange -> state [%@], code = [%d]", state ? @"Opened" : @"Fail", code);
        if (state) {
            [sdk.AVChat.VideoController openPreview];
        }
    }
```

to start the preview video.

If you want to display the preview you need to create an `ooVooVideoView` object and add it to your layout as a view when you receive `OOVOOPreviewDidStartNotification` notification you should associate `ooVooVideoView` object with video channel by calling:

```objective-c
    [self.sdk.AVChat.VideoController bindVideoRender:@"ParticipantID" render:self.videoView];
```

To stop receiving the preview video, you may call:

```objective-c
    [sdk.AVChat.VideoController closePreview];
```

To stop the camera call:

```objective-c
    [self.sdk.AVChat.VideoController closeCamera];
```

This will stop preview too if it was displayed – you will also get notified about that. <!--The sequence diagram below describes how to create video preview.--> <!--![enter image description here](https://code.oovoo.com/native/docs/ios/7_flow.png)-->

## How do I start/stop sending my audio and video streams to a conference?
There are separate API calls to turn the camera on/off, for preview control and video transmission. See below. When you are in a conference, you can decide whether to send your own AV streams into the current conference. Other participants in the conference will get notification when your AV stream becomes available or unavailable.

To **start** sending your local AV stream:

```objective-c
    [self.sdk.AVChat.VideoController startTransmitVideo];
    [self.sdk.AVChat.AudioController setRecordMuted:NO];
    [self.sdk.AVChat.AudioController setPlaybackMute:NO];
```

To **stop** sending your local AV stream:

```objective-c
    [self.sdk.AVChat.VideoController stopTransmitVideo];
    [self.sdk.AVChat.AudioController setRecordMuted:YES];
    [self.sdk.AVChat.AudioController setPlaybackMute:YES];
```

## How do I start/stop receiving the video streams of remote participants in a conference?
When you are in a conference, you can decide whether to receive one, several, or all remote participants' video streams. Each participant is identified by a corresponding Participant ID. But before you request other participant's video you also need to provide SDK with a `VideoPanel` in which the participant's video will be rendered. To **start** receiving a participant's video stream:

```objective-c
    - (void)didParticipantJoin:(id<ooVooParticipant>)participant user_data:(NSString *)user_data
    {
        [self.sdk.AVChat.VideoController bindVideoRender:participant.participantID render:panel];
        [self.sdk.AVChat.VideoController registerRemoteVideo:participant.participantID];
    }
```

When the participant's video stream has been received, you will be notificatied by the SDK indicating it is now ready to display the participant's video.

```objective-c
    -(void)didRemoteVideoStateChange:(NSString* )uid state:(ooVooAVChatRemoteVideoState)state width:(const int)width height:(const int)height error:(sdk_error)code {
    ...
    }
```

Note that this API does not give you control over a remote participant's camera and video stream. It simply allows you to subscribe to that remote participant's video stream and receive it when the participant does send its video stream into the conference. Each time the participant's video state has changed, you will receive notification.

To **stop** receiving a participant's video stream:

```objective-c
    [self.sdk.AVChat.VideoController registerRemoteVideo:participant.participantID];
```

## How do I display a remote participant’s video in my app?
To display a participant's video stream you should follow the same procedure as described in the previous section for displaying the preview video, with the only difference being that you should receive a participant id in the `OOVOOParticipantDidJoinNotification` notification you receive when a remote participant has connected to the conference.  You should connect this participant id to the desired `ooVooVideoRender` object.  <!--See the sequence diagram bellow.--> <!--![enter image description here](https://code.oovoo.com/native/docs/ios/9_flow2.png) -->

## Can I control the layout of the video windows?
In general video rendering is handled by object created within the ooVoo SDK. It is then up to the developer to place this object in your app's UI with the desired location, aspect ratio and size.

## How do I play the audio of a conference?
The ooVoo SDK provides a single mixed audio stream for each video conference. To play the audio stream of the conference, you call the following API in the SDK.

```objective-c
    [self.sdk.AVChat.AudioController setPlaybackMuted:NO];
```

You can pause the audio in a conference.

```objective-c
    [self.sdk.AVChat.AudioController setPlaybackMuted:YES];
```

## How do I select from multiple cameras?
The ooVoo SDK allows you to enumerate a list of cameras available on your device, and select the desired one for video call. In case your device has only one camera it would be selected no matter what parameter you pass.

```objective-c
    NSArray* arr_dev = [self.sdk.AVChat.VideoController getDevicesList];
    ...
    [self.sdk.AVChat.VideoController setConfig:strID forKey:ooVooVideoControllerConfigKeyCaptureDeviceId];
```

## How do I set camera video for a call?
In the ooVoo SDK 4 video resolution levels are defined: •    Low – about 176x144 (some devices do not support this resolution so the closest one to this is selected) •    Medium – about 352*240 (some devices do not support this resolution so the closest one to this is selected) •    High – 640x480 •    HD – 1280x720

Not all levels are available on every device, due to hardware capabilities. Some devices will only be capable of running at the "Low" resolution level. HD quality video is only available on devices which support hardware accelerated video encoding.

ooVoo SDK provides API for setting the desired camera resolution level. Some examples are provided below.

```objective-c
    [self.sdk.AVChat.VideoController setConfig:strID forKey:ooVooVideoControllerConfigKeyResolution];
```

## How can I use video filters within my app?
Video filters provide overlays and other modifications to the user's video which allow you to modify the look of the video for special effects, fun, etc. You can get an array of all the available video filters using:

```objective-c
    NSArray* arr_dev = [self.sdk.AVChat.VideoController getEffectsList];
```

Once you have a list of the available filters, you can turn on a specific video filter by calling:

```objective-c
    [self.sdk.AVChat.VideoController setConfig:strID forKey:ooVooVideoControllerConfigKeyEffectId];
```

If you'd like to check which filter is currently active you can check:

```objective-c
    [self.sdk.AVChat.VideoController getConfig:ooVooVideoControllerConfigKeyEffectId];
```

This will return an NSString with the name of the filter that is currently being used.

## How can I send messages while in a call?
In-call messaging capability in ooVoo SDK enables sending of messages to participants in a conference. This can be used to implement features such as in-chat text messaging or can serve as a channel to send text based control messages that can be triggered, or listened for, by some activity within the app.

You can check whether the in-call message capability is enabled for your current application by checking the value of:

```objective-c
    [ooVooClient sharedInstance].inCallMessagesPermitted;
```

This returns a Boolean value of either YES or NO and will let you know if this capability is enabled for your current application.

You can send messages by calling the controller in the following way and specifying which participantID you'd like to send a message to. If you'd like to send a message to all participants of a conference you can do so by calling the following with a nil participantID:

```objective-c
    [self.sdk.AVChat.sendData  message: message completion:(CompletionHandler)completion;
```

The incaming messages you will received by AVChat delegate method

```objective-c
    -(void)didReceiveData:(NSString* )uid data:(NSData* )data;
```

## What events fired during a conference should my app pay attention to?
The events your app may receive during a conference consist of the following categories: •    Conference status change: e.g., participant joins, leave the conference. •    Participant status change: e.g., participant's audio video stream turned on/off. •    Connection status change: e.g., reporting connection quality issues. •    Application status: e.g., ooVoo SDK errors. Check out the ooVoo SDK API documentation and header files for details.

## How do I leave a conference?
You can leave a conference by issuing the following API call:

```objective-c
    [self.sdk.AVChat leave];
```

You will be notified if you have successfully disconnected from the conference.

```objective-c
    -(void)didConferenceStateChange:(ooVooAVChatState)state error:(sdk_error)code {
    ...
    }
```

After you have been disconnected from the conference, other participants remaining in the conference will get notification and will no longer receive your audio video stream.

## How do I close a conference?
An ooVoo conference is closed automatically by the ooVoo cloud service when there is no participant connected in the conference (i.e., all participants have left). No explicit API call is needed.

## How do I handle incoming phone calls during a conference?
You do not need to do anything! When a user answers a phone call we automatically enter into HOLD mode where we release the audio device to allow the phone to use it. You will also get

```objective-c
    - (void)didAudioTransmitStateChange:(BOOL)state error:(sdk_error)code;
    - (void)didAudioReceiveStateChange:(BOOL)state error:(sdk_error)code;
```

```
when state of audio will set to false and sdk_error to sdk_error_Held value
```

When the phone call ends and the application returns to foreground we return from HOLD mode and you get:

```objective-c
    - (void)didAudioTransmitStateChange:(BOOL)state error:(sdk_error)code;
    - (void)didAudioReceiveStateChange:(BOOL)state error:(sdk_error)code;
```

```
when state of `audio` will set to true and `sdk_error` to `sdk_error_Held value`.
```

## How do I handle call security with my app?
To check if SSL certificate verification is enabled call  sslVerifyPeer which returns YES if it enabled or NO in other case.

```objective-c
    [ooVooClient sharedInstance].sslVerifyPeer;
```

To enable or bypass SSL certificates verification use property sslVerifyPeer. Default is true. Disabling verification is temporary until re-initialization of SDK.

```objective-c
    [ooVooClient sharedInstance].sslVerifyPeer= verify; // verify – YES or NO
```

## How do I check if specific resolution level supported by all devices in call?
To check if specific resolution would be available to display on all devices in conference call isResolutionSupported which returns YES if it enabled or NO in other case.

```objective-c
    [[ooVooClient sharedInstance].AVChat isResolutionSupported:ResolutionLevelMed];
```

## How do I check if specific resolution level supported by my device?

```objective-c
    [[ooVooClient sharedInstance].AVChat.VideoController.activeDevice isResultionSupported:ResolutionLevelMed] ;
```

## How do I change the output device for audio playback?
We are strictly following default iOS behavior and do not do anything special or different from what you already know. The only setting that can affect audio routing is changing the conference mode: in `ooVooModeAudioConference`  mode the default output is to earpiece, in `ooVooModeVideoConference` mode the default is speaker and you cannot route to earpiece.

For sample code how we create UI to control audio routing please search for usage of MPVolumeView class in source code of sample application.

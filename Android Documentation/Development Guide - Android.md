# Developing With the Android SDK
<!-- MarkdownTOC -->

- [How can I get an Application ID and Application Token?](#how-can-i-get-an-application-id-and-application-token)
- [How do I connect my users in a video call?](#how-do-i-connect-my-users-in-a-video-call)
- [Configuring SDK](#configuring-sdk)
- [How do I create/join a conference?](#how-do-i-createjoin-a-conference)
- [How can I understand what error messages mean?](#how-can-i-understand-what-error-messages-mean)
- [How do I use the logger interface to capture device logs?](#how-do-i-use-the-logger-interface-to-capture-device-logs)
- [How can I configure audio route mode (i.e. enable audio only calls)?](#how-can-i-configure-audio-route-mode-ie-enable-audio-only-calls)
- [How do I display my local preview video in my app?](#how-do-i-display-my-local-preview-video-in-my-app)
- [How do I start/stop sending my audio and video streams to a conference?](#how-do-i-startstop-sending-my-audio-and-video-streams-to-a-conference)
- [How do I start/stop receiving the video streams of remote participants in a conference?](#how-do-i-startstop-receiving-the-video-streams-of-remote-participants-in-a-conference)
- [How do I display a remote participant's video in my app?](#how-do-i-display-a-remote-participant's-video-in-my-app)
- [How do I control the layout of the video windows?](#how-do-i-control-the-layout-of-the-video-windows)
- [How do I init the audio of a conference?](#how-do-i-init-the-audio-of-a-conference)
- [How do I play the audio of a conference?](#how-do-i-play-the-audio-of-a-conference)
- [How do I select from multiple cameras?](#how-do-i-select-from-multiple-cameras)
- [How do I set video resolution for a call?](#how-do-i-set-video-resolution-for-a-call)
- [How Can I use video filters within my app?](#how-can-i-use-video-filters-within-my-app)
- [How can I send messages while in a call?](#how-can-i-send-messages-while-in-a-call)
- [What events fired during a conference should my app pay attention to?](#what-events-fired-during-a-conference-should-my-app-pay-attention-to)
- [How do I leave a conference?](#how-do-i-leave-a-conference)
- [How do I close a conference?](#how-do-i-close-a-conference)
- [How do I handle incoming phone calls?](#how-do-i-handle-incoming-phone-calls)
- [How do I handle call security with my app?](#how-do-i-handle-call-security-with-my-app)
- [How do I get notification that audio routing has changed to different device?](#how-do-i-get-notification-that-audio-routing-has-changed-to-different-device)
- [How do I route audio to a different device?](#how-do-i-route-audio-to-a-different-device)
- [How do I check if a specific resolution level is supported by all devices in call?](#how-do-i-check-if-a-specific-resolution-level-is-supported-by-all-devices-in-call)
- [How do I check if a specific resolution level is supported by active camera?](#how-do-i-check-if-a-specific-resolution-level-is-supported-by-active-camera)
- [How do I get list of video cameras on my device?](#how-do-i-get-list-of-video-cameras-on-my-device)
- [How do I change camera from one to other ?](#how-do-i-change-camera-from-one-to-other-)
- [How do I enable bluetooth audio ?](#how-do-i-enable-bluetooth-audio-)

<!-- /MarkdownTOC -->


## How can I get an Application ID and Application Token?
Application ID and Application Token are unique identifiers assigned by ooVoo for each developer. They are required for accessing the ooVoo video cloud service via the ooVoo SDK. After you have successfully signed up to become an ooVoo SDK developer, you should receive email from us to verify your address. Once verification is complete, you will be able to log into the developer dashboard at [http://developer.oovoo.com](http://developer.oovoo.com) and generate AppIDs and Tokens.

Application ID and Application Token are the only way ooVoo uses to identify you as a unique and legitimate ooVoo SDK developer. You must exercise caution to keep them secure. If you ever forget/lose your ID and/or Token, please contact ooVoo by emailing to sdk.support@oovoo.com or contact your designated ooVoo developer advocate immediately.

## How do I connect my users in a video call?
In ooVoo a video call is technically named as _"conference"_. Each conference is identified by a unique _"Conference ID"_. To connect two or more users of your application in a video call, you simply put those users in the same ooVoo conference by having them joining conference using the same Conference ID. It should be noted that ooVoo SDK does not handle the "signaling" steps per se between the end users of your application. It is up to you the developer to manage the distribution of the corresponding Conference ID to the target end user(s) by your own application logic.

## Configuring SDK
The ooVoo SDK provides you an object through which you can access most of the functionality provided by SDK. This is the _entry point_ into the SDK:

```java
ooVooClient.sharedInstance();
```

Before you can start calling methods with the SDK you should provide it with Android application context and setup the logger callback (so that you can see what happens inside):

```java
import com.oovoosdk.api.ooVooClient;
    ...
    public class MyApplication extends Application{
    ...
    private ooVooClient sdk = null;
    ..
    public void onCreate(){
        ...
        ooVooClient.setContext(this);
        ooVooClient.setLogger(this, LogLevel.Debug);
        sdk = ooVooClient.sharedInstance();
        ...
    }
```

Now you need to authorize to the ooVoo Video Platform backend services - this sets up the SDK with all functionality and permissions allowed for your application:

```java
sdk.authorizeClient(token, "application version", new ooVooSdkResultListener() {
        @Override
        public void onResult(ooVooSdkResult result) {
          if (result.getResult() == sdk_error.OK) {
             // You are authorized!
          }
          else
          {
            //Oops, you are not authorized , you can see reason of error by call result.getDescription()
          }
    });
```

Now you have to login to the ooVoo Video Platform backend service - which will assign you a session token:

```java
sdk.getAccount().login("username", new ooVooSdkResultListener() {
        @Override
        public void onResult(ooVooSdkResult autorize_result) {
          if (autorize_result.getResult() == sdk_error.OK) {
            // You are logged in
          }
          else{
            // An error happened
          }
    });
```

## How do I create/join a conference?
Technically, there is no difference between being the first to join a conference (creating it) and being second or third (joining an existing conference). The ooVoo Video Platform handles all backend setup and makes it transparent to the user.

All you need to do is to provide the same _Conference ID_ to all clients that you want to join the same conference. If the Conference ID already exists, the user will be added to the existing conference identified by the Conference ID and your app will receive a notification from the SDK indicating if the join conference action was successful.

In order for SDK to notify you about state of the conference you need to setup an event listener first. There are 3 interfaces that provide you with events:
- `AVChatListener` provides you with events about the conference itself and other participants
- `AudioControllerListener` provides events about your audio
- `VideoControllerListener` provides events about your video

For simplicity we demonstrate a single class that implements all 3 interfaces:

```java
import com.oovoosdk.interfaces.AVChatListener;
import com.oovoosdk.interfaces.AudioControllerListener;
import com.oovoosdk.interfaces.VideoControllerListener;
import com.oovoosdk.interfaces.AudioRouteControllerListener;
...
public class ooVooSDKEvents implements AVChatListener, VideoControllerListener, AudioControllerListener,AudioRouteControllerListener {
        private ooVooClient  sdk      = null;
        ...
        sdk = ooVooClient.sharedInstance();
        sdk.getAVChat().setListener(this);
        sdk.getAVChat().getVideoController().setListener(this);
        sdk.getAVChat().getAudioController().setListener(this);
        sdk.getAVChat().getAudioController().getAudioRouteController().setListener(this);
        ....
    }
```

Now you are ready to make a call:

```java
    ...
    sdk.getAVChat().join("Conference ID", "Participant Data"); // Participant Data is optional information you can pass to ooVoo SDK.
    ...
```

You will get following event called on AVChatListener interface:

```java
    @Override
    public void onConferenceStateChanged(ConferenceState state, sdk_error err) {
        if (state == ConferenceState.Joined && err == sdk_error.OK) {
            //You are joined in a conference
        }
        else if (state == ConferenceState.Joined && err != sdk_error.OK) {
            //You are not joined in a conference because an error occured
        }
    }
```

If you got `ConferenceState.Joined` then technically you are already in the conference. You will start getting events about other participants asyncronously. Also, at this point, you can start audio/video. Other participants in the conference will also get notified that a new user, identified by a unique Participant ID assigned by ooVoo to represent your identity in the conference, has joined.

## How can I understand what error messages mean?
If for some reason your app returns an error message, you can easily display what that error messages means in the UI using the following. Make sure you assign this to a string variable or typecast it as we do below:

```java
public abstract String getErrorMessageForConferenceCoreError(sdk_error error);
```

## How do I use the logger interface to capture device logs?
The Logger interface allows you to implement client side logging for your mobile devices to assist in troubleshooting and information gathering. In order to utilize the logger, implement the following interface:

```java
    public interface LoggerListener {
            void OnLog(LogLevel level, String tag, String message);
    }
```

## How can I configure audio route mode (i.e. enable audio only calls)?
To set audio or video audio route mode call `setAudioRouteMode (AudioRouteMode mode)`, mode can be AudioRouteModeVoiceChat or AudioRouteModeVideoChat. This must be called before `joinConference`.

```java
    sdk.getAVChat().getAudioController().setAudioRouteMode (AudioRouteMode.AudioRouteModeVideoChat);
```

## How do I display my local preview video in my app?
Our SDK allows you to open the video preview before joining a conference. There is separate API to turn the camera on/off, preview control and video transmission.

To display preview you need to first create or add to xml layout com.oovoo.sdk.api.ui.VideoPanel,

Before you join a conference, you may call `openCamera()` method of `VideoController` interface to turn on your camera and then `OpenPreview()` to turn on the video preview. You may call `closeCamera()` to turn off preview.

To assign view `com.oovoo.sdk.api.ui.VideoPanel` you call `bindPreviewRender("your_user_id",view)` method of `VideoController`. <!-- The sequence diagram below describes how to create video preview.-->

## How do I start/stop sending my audio and video streams to a conference?
There are separate APIs to turn the camera on/off, preview control and video transmission. Please update your code accordingly as follows.

When you are in a conference, you can decide whether to send your own AV streams into the current conference. Other participants in the conference will get a notification when your AV stream becomes available or unavailable.

To start sending your local AV stream you should first start your preview as described above and then call `startTransmit()`:

```java

    sdk.getAVChat().getVideoController().bindRender("ParticipantID"/*also you can pass here null for preview*/,com.oovoo.sdk.app.ui.VideoPanel/*or you own object inheritance from our VideoPanel*/);
    sdk.getAVChat().getVideoController().openCamera();

    ...
    //You will get following event called on AVChatListener interface:

    @Override
    public void onCameraStateChanged(boolean state, String devideId, int width, int height, int fps, sdk_error err) {
        if(state == true) // Camera device was opened succussfully
        {
            sdk.getAVChat().getVideoController().openPreview();
            sdk.getAVChat().getVideoController().startTransmit();
        }
        else {
            //An error happened when we try to open camera
        }
    }
```

To **stop** sending your local AV stream:

```java
    sdk.getAVChat().getVideoController().stopTransmit();
```

To close your preview and video device call:

```java
sdk.getAVChat().getVideoController().closePreview();
sdk.getAVChat().getVideoController().closeCamera();
```

## How do I start/stop receiving the video streams of remote participants in a conference?
When you are in a conference, you can decide whether to receive one, several, or all remote participants' video streams. Each participant is identified by a corresponding Participant ID.

To **start** receiving a participant's video stream:

```java
    sdk.getAVChat().getVideoController().registerRemote(“ParticipantID”);
```

When the participant's video stream has been received, you will get events/notification from the SDK on the AVChatListener interface indicating it is now ready to display the participant's video.

Note that this API does not give you control over a remote participant's camera and video stream. It simply allows you to subscribe to that remote participant's video stream and receive it when the participant does send its video stream into the conference. Each time the participant's video state has changed, you will receive notification.

To **stop** receiving a participant's video stream:

```java
sdk.getAVChat().getVideoController().unregisterRemote(“ParticipantID”);
```

## How do I display a remote participant’s video in my app?
To display a participant's video you need to first create or add to xml layout `com.oovoo.sdk.interfaces.VideoRender`.

After you join a conference, or a new participant joins the conference, you will receive an `onParticipantJoined()` callback for each participant (identified by a unique participantId you receive with the callback) currently in the conference.

You can call the `registerRemote(participantId)` method of `VideoController` to start receiving a specific participant's video stream. If successful, you should receive `onRemoteVideoStateChanged` callback. (Similarly, we can call `unregisterRemote(participantId)` to stop receiving.)

```java
@Override
public void onParticipantJoined(Participant participant, String displayName) {
    sdk.getAVChat().getVideoController().bindRender(participant.getID(), videoPanel);
    sdk.getAVChat().getVideoController().registerRemote(participant.getID());
}
```

<!-- The sequence diagram below describes how to displaying a participant’s
> video using ooVoo SDK.-->

## How do I control the layout of the video windows?
In general, video rendering is handled by an object created within the ooVoo SDK. It is then up to the developer to place this object in your app's UI with the desired location, aspect ratio and size.

Video is rendered inside `com.oovoo.sdk.app.ui.VideoPanel`. The VideoPanel implemented a native renderer.

Use the Android layout mechanism to place your preview or participant video view in the xml layout file or in java code.

```xml
<com.oovoo.sdk.api.ui.VideoPanel
    android:id="@+id/full_screen_video_panel"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="4dip">
</com.oovoo.sdk.api.ui.VideoPanel>
```

You can implement your renderer using inheritance or aggregation of our VideoPanel object.  

## How do I init the audio of a conference?
To start using local audio (mic/speaker) you must first init audio by calling initAudio from audio controller

```java
sdk.getAVChat().getAudioController().initAudio(new ooVooSdkResultListener() {
    public void onResult(ooVooSdkResult init_audio_result){
        if(init_audio_result.getResult() == sdk_error.OK){
            //Audio API was inited successfully
        }
        else
        {
            //An error occurred
        }
    }
});
```

## How do I play the audio of a conference?
The ooVoo SDK provides a single mixed audio stream for each video conference. To play the audio stream of the conference, you call the following API in the SDK.

```java
sdk.getAVChat().getAudioController().setPlaybackMuted(false);
```

You can pause the audio in a conference.

```java
sdk.getAVChat().getAudioController().setPlaybackMuted(true);
```

Also it is possible to get list of available audio routes and set particular audio route (Earpiece, Speaker, Headset and Bluetooth).  

```java
AudioRouteController audioRouteController = sdk.getAVChat().getAudioController().getAudioRouteController();
Vector<AudioRoute> routes = audioRouteController.getRoutes(); // Get list of audio routes
audioRouteController.setRoute(AudioRoute.Speaker); // Set audio route to speaker
```

To receive notification about changing audio route, set listener and implement callback `onAudioRouteChanged` as showing below.

```java
audioRouteController.setListener(listener);
@override
public void onAudioRouteChanged(AudioRoute oldRoute, AudioRoute newRoute) {
      //Do something here

}
```

## How do I select from multiple cameras?
The ooVoo SDK allows you to enumerate a list of cameras available on your device, and select the desired one for the video call. In case your device has only one camera it would be selected no matter what parameter you pass.

```java
sdk.getAVChat().getVideoController().setActiveDevice(device);
```

## How do I set video resolution for a call?
In the ooVoo SDK 4 video resolution levels are defined: •    Low – about 176x144 (some devices do not support this resolution so the closest one to this is selected) •    Medium – about 352*240 (some devices do not support this resolution so the closest one to this is selected) •    High – 640x480 •    HD – 1280x720

Not all levels are available on every device, due to hardware capabilities and limitations. Some devices will only be capable of running at the "Low" resolution level. HD quality video is only available on devices which support hardware accelerated video encoding.

The ooVoo SDK provides API for setting the desired camera resolution level. Some examples are provided below.

```java
sdk.getAVChat().getVideoController().setActiveResolution(VideoController.CameraResolutionLevel.ResolutionMedium);
```

To check if video resolution is supported in video conference use method provided below.

```java
boolean supported = sdk.getAVChat().getVideoController().isResolutionSupported(VideoController.CameraResolutionLevel.ResolutionMedium);
```

## How Can I use video filters within my app?
Video filters provide overlays and other modifications to the users video which allow you to modify the look of the video for special effects, fun, etc.

You can get an array of all the available video filters using:

```java
sdk.getAVChat().getVideoController().getEffectList();
```

Once you have a list of all the available filters, you can turn on a specific video filter by calling:

```java
sdk.getAVChat().getVideoController().setActiveEffect(effectId);
```

If you'd like to check which filter is currently active you can check:

```java
sdk.getAVChat().getVideoController().getActiveEffect();
```

This will return an object describing the filter that is currently being used.

## How can I send messages while in a call?
This functionality enables the sending of messages to participants in chat. This can be used to implement features such as in-chat text messaging or can serve as a channel to send text based control messages that can be triggered, or listened for, by some activity within the app.

You can check whether the in-call message capability is enabled for your current application by checking the value of:

```java
sdk.getAVChat().send();
```

This returns a Boolean value and will let you know if this capability is enabled for you current application. You can send messages to either all participants in a conference or only to one specific participant. To send a message to ALL participants of a conference:

```java
sdk.getAVChat().send(message); //(Your message text is a byte array)
```

To send a message to a specific participant:

```java
sdk.getAVChat().send("ParticipantID",message);
```

Your app will receive notification from the SDK indicating a received message:

```java
@override
public void onReceiveData(String participantId, byte[] buffer) {}
```

## What events fired during a conference should my app pay attention to?
The events your app may receive during a conference consist of the following categories: •    Conference status change: e.g., participant join or leave the conference. •    Participant status change: e.g., participant's video stream turned on/off. •    Connection quality status change: e.g., reporting connection quality issues. •    Application status: e.g., ooVoo SDK errors.

Check out the ooVoo SDK API documentation and header files for details.

## How do I leave a conference?
You can leave a conference by issuing the following API call:

```java
sdk.getAVChat().leave();
```

You will be notified if you have successfully disconnected from the conference.

```java
public void onConferenceStateChanged(AVChatListener.ConferenceState state, sdk_error err);
```

After you have been disconnected from the conference, other participants remaining in the conference will get notification and will no longer receive your audio video stream.

```java
public void onParticipantLeft(String participantId) ;
```

## How do I close a conference?
An ooVoo conference is closed automatically by the ooVoo cloud service when there is no participant connected in the conference (i.e., all participants have left). No explicit API call is needed.

## How do I handle incoming phone calls?
You do not need to do anything! When a user answers a phone call we automatically enter into HOLD mode where we release the audio device to allow the phone to use it. You will also get a callbacks:

```java
onAudioReceiveStateChanged(boolean state, sdk_error error) and onAudioTransmitStateChanged(boolean state, sdk_error error)
```

When the phone call ends and the application returns to foreground we return from HOLD mode and you get

```java
onAudioReceiveStateChanged(boolean state, sdk_error error) and onAudioTransmitStateChanged(boolean state, sdk_error error)
```

## How do I handle call security with my app?
To check if SSL certificate verification is enabled call getSslVerifyPeer which returns true if enabled or false in other case.

```java
sdk.isSslPeerVerify()
```

To enable or bypass SSL certificates verification use method setSslVerifyPeer. Default is true. Disabling verification is temporary until re-initialization of SDK.

```java
sdk.setSslPeerVerify (verify); // verify – true of false
```

## How do I get notification that audio routing has changed to different device?
Set a new listener in AudioRouteController that implements `AudioRouteControllerListener`

```java
sdk.getAVChat().getAudioController().getAudioRouteController().setListener(yourlistener);
```

## How do I route audio to a different device?
To route audio to/from a different device you have to use the AudioRouteController interface.

```java
Vector<AudioRouteController.AudioRoute> routes = sdk.getAVChat().getAudioRouteController().getRoutes();
…//select item to route to
sdk.getAVChat().getAudioRouteController().setRoute(audioRoute);
```

## How do I check if a specific resolution level is supported by all devices in call?
To check if a specific resolution would be available to display on all devices in conference call isResolutionSupportedInConference which returns true if it is enabled or false in the case.

```java
sdk.getAVCHat().isResolutionSupported(aResolutionLevel. ResolutionMedium);
```

## How do I check if a specific resolution level is supported by active camera?

```java
sdk.getAVChat().getVideoController().getActiveDevice().isResolutionSupported(aResolutionLevel.ResolutionMedium);
```

## How do I get list of video cameras on my device?

```java
ArrayList<VideoDevice> devices = sdk.getAVChat().getVideoController().getDevices() ;
```

## How do I change camera from one to other ?

```java
sdk.getAVChat().getVideoController().setActiveDevice(video_device);
```

## How do I enable bluetooth audio ?

```xml
Simply add the necessary permissions in the AndroidManifest.xml of your application

<uses-permission android:name="android.permission.BLUETOOTH"/>
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN"/>
<uses-permission android:name="android.permission.BLUETOOTH_PRIVILEGED"/>
```

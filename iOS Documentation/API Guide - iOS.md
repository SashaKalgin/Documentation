#iOS API Guide

Table Of Contents
<!-- TOC depth:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [iOS API Guide](#ios-api-guide)
- [ooVooClient Interface](#oovooclient-interface)
	- [sharedInstance](#sharedinstance)
	- [setLogger](#setlogger)
	- [setLogLevel](#setloglevel)
	- [setClientVersion](#setclientversion)
	- [authorizeClient](#authorizeclient)
	- [Properties](#properties)
		- [IsAuthorized](#isauthorized)
		- [Account](#account)
		- [AVChat](#avchat)
- [ooVooClientLogger Protocol](#oovooclientlogger-protocol)
	- [onLog](#onlog)
- [Account Protocol](#account-protocol)
	- [login](#login)
	- [logout](#logout)
	- [Properties](#properties)
		- [uid](#uid)
		- [state](#state)
- [AVChat Protocol](#avchat-protocol)
	- [join](#join)
	- [leave](#leave)
	- [sendData](#senddata)
	- [sendData](#senddata)
	- [Properties](#properties)
		- [VideoController](#videocontroller)
		- [AudioController](#audiocontroller)
		- [delegate](#delegate)
	- [AVChatDelegate](#avchatdelegate)
		- [didParticipantJoined](#didparticipantjoined)
		- [didParticipantLeft](#didparticipantleft)
		- [didConferenceStateChanged](#didconferencestatechanged)
		- [didReceiveData](#didreceivedata)
- [VideoController](#videocontroller)
	- [setConfig](#setconfig)
	- [setConfig](#setconfig)
	- [getDevicesList](#getdeviceslist)
	- [getEffectsList](#geteffectslist)
	- [bindVideoRender](#bindvideorender)
	- [unbindVideoRender](#unbindvideorender)
	- [registerRemoteVideo](#registerremotevideo)
	- [unregisterRemoteVideo](#unregisterremotevideo)
	- [startTransmitVideo](#starttransmitvideo)
	- [stopTransmitVideo](#stoptransmitvideo)
	- [isVideoTransmitted](#isvideotransmitted)
	- [openCamera](#opencamera)
	- [closeCamera](#closecamera)
	- [openPreview](#openpreview)
	- [closePreview](#closepreview)
	- [Properties](#properties)
		- [VideoSources](#videosources)
		- [delegate](#delegate)
	- [VideoControllerDelegate Protocol](#videocontrollerdelegate-protocol)
		- [didCameraStateChanged](#didcamerastatechanged)
		- [didVideoTransmitStateChanged](#didvideotransmitstatechanged)
		- [didRemoteVideoStateChanged](#didremotevideostatechanged)
		- [didVideoPreviewStateChanged](#didvideopreviewstatechanged)
		- [didActiveDeviceChanged](#didactivedevicechanged)
- [AudioController Protocol](#audiocontroller-protocol)
	- [initAudio](#initaudio)
	- [setConfig](#setconfig)
	- [getConfig](#getconfig)
	- [isPlaybackMuted](#isplaybackmuted)
	- [setPlaybackMute](#setplaybackmute)
	- [isRecordMuted](#isrecordmuted)
	- [setRecordMute](#setrecordmute)
	- [getRecorderDevicesList](#getrecorderdeviceslist)
	- [getPlaybackDevicesList](#getplaybackdeviceslist)
	- [Properties](#properties)
		- [delegate](#delegate)
		- [MicVolume](#micvolume)
		- [SpeakerVolume](#speakervolume)
	- [AudioControllerDelegate](#audiocontrollerdelegate)
		- [didAudioTransmitStateChanged](#didaudiotransmitstatechanged)
		- [didAudioReceiveStateChanged](#didaudioreceivestatechanged)
		- [didActiveDeviceChanged](#didactivedevicechanged)
		- [didAudioDeviceStateChanged](#didaudiodevicestatechanged)
	- [AudioControllerConfigKey](#audiocontrollerconfigkey)
- [Effect Protocol](#effect-protocol)
	- [Properties](#properties)
		- [effectName](#effectname)
		- [effectId](#effectid)
		- [iconUrl](#iconurl)
	- [VideoConfigKey](#videoconfigkey)
- [Device Protocol](#device-protocol)
	- [Properties](#properties)
	- [deviceName](#devicename)
	- [deviceId](#deviceid)

<!-- /TOC -->


# ooVooClient Interface
## sharedInstance
**Description**: create single ooVooClient instance.

**Parameters**: N/A

**Result**: return singleton ooVooClient object.

## setLogger
**Description**: Associates a logging object with the SDK.

**Parameters**:

Attribute | Type                | Requirements | Description
--------- | ------------------- | ------------ | -----------------
logger Id | `ooVooClientLogger` | Required     | The log recipient

**Result**: no result.

## setLogLevel
**Description**: Use this method to specify the verbosity of log messages you wish to receive and handle on the client end.

**Parameters**:

Attribute | Type       | Requirements | Description
--------- | ---------- | ------------ | ------------------------------------------------
level     | `LogLevel` | Required     | The minimal level of log messages to be received

**Result**: no result.

## setClientVersion
**Description**: set client version (SDK user).

**Parameters**:

Attribute      | Type         | Requirements | Description
-------------- | ------------ | ------------ | ----------------
Client version | `NSString *` | Required     | SDK user version

## authorizeClient
**Description**: Authorize access to ooVooClient API.

**Parameters**:

Attribute         | Type                | Requirements | Description
----------------- | ------------------- | ------------ | -------------------------------
application_token | `NSString *`        | Required     | The application token got after
completion        | `CompletionHandler` | Required     | Answer result callback

**Result**: no result.

## Properties
### IsAuthorized
**Description**: atomic and read only property. Return if current client is authorized.

**Parameters**: no parameters.

**Result**: authorization status: true for yes otherwise false.

### Account
**Description**: Get read only ooVoo client account property. Use account object to perform operations such as: login, logout.

**Parameters**: N/A.

**Result**: returns reference to object that implements Account protocol.

### AVChat
**Description**: Get read only ooVoo audio video property. Use AVChat to perform operation such as: join, leave conference.

**Parameters**: N/A.

**Result**: returns reference to object that implements AVChat protocol.

# ooVooClientLogger Protocol
## onLog
**Description**: call back function that should handle the log from SDK.

**Parameters**:

Attribute | Type         | Requirements | Description
--------- | ------------ | ------------ | ---------------------------------
Level     | LogLevel     | Required     | The log level, error, debug, info
Log       | `NSString *` | Required     | Answer result callback

**Result**: N/A

# Account Protocol
## login
**Description**: Login with an existing user.

**Parameters**:

Attribute  | Type                | Requirements | Description
---------- | ------------------- | ------------ | ----------------------------------------
USerID     | `NSString *`        | Required     | The account unique id, no less 6 symbols
completion | `CompletionHandler` | Required     | Answer result callback

**Result**: no result.

## logout
**Description**: Logout from ooVoo client account.

**Parameters**: no parameters

**Result**: no results.

## Properties
### uid
**Description**: read only property which returns account id.

**Parameters**: no parameters

**Result**: account id.

### state
**Description**: read only property which returns account login state.

**Parameters**: no parameters

**Result**: account id.

# AVChat Protocol
## join
**Description**: Join conference call.

**Parameters**:

Attribute | Type         | Description
--------- | ------------ | -------------
**cID**   | `NSString *` | Conference id
**data**  | `NSString *` | User data

**Result**: N/A

## leave
**Description**: Leave conference call.

**Parameters**: N/A

**Result**: no result

## sendData
**Description**: Send a custom data to specific participant in the conference.

**Parameters:**

Attribute  | Type         | Description
---------- | ------------ | ------------------------
**uid**    | `NSString *` | User id
**Buffer** | `NSString *` | Buffer with data to send

**Result**: no result

## sendData
**Description**: Send a custom data to all participants in the conference.

**Parameters**:

Attribute  | Type         | Description
---------- | ------------ | ------------------------
**Buffer** | `NSString *` | Buffer with data to send

**Result**: no result

## Properties
### VideoController
**Description** Get read only video controller property. Use video controller to perform operations such as: open camera, open preview....

**Parameters**: N/A

**Result**: returns reference to object that implements VideoController protocol.

### AudioController
**Description**: Get read only audio controller property. Use video controller to perform operations such as: open mute speaker/microphone, get device list...

**Parameters**: N/A

**Result**: returns reference to object that implements AudioController protocol.

### delegate
**Description**: sdk user must set id<AVChatDelegate> in order to receive completion events of AVChat methods such as join, leave...

**Parameters**:

Attribute    | Type             | Description
------------ | ---------------- | -----------------------------------------------------
**delegate** | `AVChatDelegate` | user object, which implements AVChatDelegate protocol

**Result**: N/A

## AVChatDelegate
### didParticipantJoined
**Description**: Event occurs when participant joined conference.

**Parameters**:

Attribute    | Type         | Description
------------ | ------------ | -----------
**uid**      | `NSString *` | User id
**userData** | `NSString *` | UserData

**Result**: No Results

### didParticipantLeft
**Description**: Event occurs when participant left conference.

**Parameters**:

Attribute    | Type         | Description
------------ | ------------ | -----------
**uid**      | `NSString *` | User id
**userData** | `NSString *` | UserData

**Result**: No Results

### didConferenceStateChanged
**Description**: Event occurs when user joined or disconnected from conference.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | ------------------------------------------------
**state**     | `NSString *` | Enumerator which indicates conference new state.
**errorCode** | `NSString *` | Conference error code

**Result**: No Results

### didReceiveData
**Description**: Event occurs when user receive data from remote participants.

**Parameters**:

Attribute | Type         | Description
--------- | ------------ | -----------
**uid**   | `NSString *` | User id
**data**  | `NSData*`    | message

# VideoController
## setConfig
**Description**: User can set configuration of the following: capture device, resolution, FPS, effect.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
**val**   | `NSString *`               | value
**key**   | `VideoControllerConfigKey` | Configuration option

**Result**: N/A

## setConfig
**Description**: User can find configuration of the following: capture device, resolution, FPS, effect.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
**key**   | `VideoControllerConfigKey` | Configuration option

**Result**: value of chosen configuration

## getDevicesList
**Description**: Get list of connected camera devices

**Parameters**: N/A

**Result**: NSArray * array. The array holds the current connected video cameras

## getEffectsList
**Description**: Get available effect list

**Parameters**: N/A

**Result**: NSArray * array. The array holds the current available effects

## bindVideoRender
**Description**: Add remote participant video to conference.

**Parameters**:

Attribute  | Type          | Description
---------- | ------------- | --------------
**uid**    | `NSString *`  | User id
**Render** | `VideoRender` | Video renderer

**Results**: No results

## unbindVideoRender
**Description**: Remove remote participant video from conference.

**Parameters**:

Attribute  | Type          | Description
---------- | ------------- | --------------
**uid**    | `NSString *`  | User id
**Render** | `VideoRender` | Video renderer

**Result**: no result.

## registerRemoteVideo
**Description**: Register remote user for receiving participant remote video.

**Parameters**:

Attribute | Type         | Description
--------- | ------------ | -----------
**uid**   | `NSString *` | User id

**Results**: No results

## unregisterRemoteVideo
**Description**: Un-register user from stop receiving participant remote video.

**Parameters**:

Attribute | Type         | Description
--------- | ------------ | -----------
**uid**   | `NSString *` | User id

**Results**: No results

## startTransmitVideo
**Description**: Start transmitting local video to conference.

**Parameters**: N/A

**Result**: no result.

## stopTransmitVideo
**Description**: Stop transmitting local video to conference.

**Parameters**: N/A

**Result**: no result.

## isVideoTransmitted
**Description**: Get video transmitted current state

**Parameters**: no parameters.

**Result**: true for transmitted otherwise false.

## openCamera
**Description**: Turn on Camera.

**Parameters**: N/A

**Result**: no result.

## closeCamera
**Description**: Turn off camera.

**Parameters**: N/A

**Result**: no result.

## openPreview
**Description**: Start preview view. Camera must be opened before opening preview

**Parameters**: N/A

**Result**: no result.

## closePreview
**Description**: Close preview view.

**Parameters**: N/A

**Result**: no result.

## Properties
### VideoSources
**Description**: Get a dictionary of current VideoSources (key is the UID of the VideoSource). This property also allows subscribing for list changes.

**Result**: list of VideoSources.

### delegate
**Description**: sdk user must set id<VideoControllerDelegate> in order to receive completion events of VideoController methods such as join, leave...

**Parameters**:

Attribute    | Type                      | Description
------------ | ------------------------- | -----------------------------
**delegate** | `VideoControllerDelegate` | user object, which implements | VideoControllerDelegate protocol

**Result**: N/A

## VideoControllerDelegate Protocol
### didCameraStateChanged
**Description**: Event fired when system detects that camera state was changed.

**Parameters**:

Attribute     | Type       | Description
------------- | ---------- | ----------------
**state**     | `BOOL`     | Camera new state
**errorCode** | `uint32_t` | Error code

**Result**: no result.

### didVideoTransmitStateChanged
**Description**: Event fired when video transmit state was changed.

**Parameters**:

Attribute     | Type       | Description
------------- | ---------- | ------------------------
**state**     | `BOOL`     | Video transmit new state
**errorCode** | `uint32_t` | Error code

**Result**: no result.

### didRemoteVideoStateChanged
**Description**: Event fired when remote user video transmit state was changed.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | ------------------------
uid           | `NSString *` | Remote user id
**state**     | `BOOL`       | Video transmit new state
**errorCode** | `uint32_t`   | Error code

**Result**: no result.

### didVideoPreviewStateChanged
**Description**: Event fired when preview video state was changed.

**Parameters**:

Attribute     | Type       | Description
------------- | ---------- | ------------------------
**state**     | `BOOL`     | Video transmit new state
**errorCode** | `uint32_t` | Error code

**Result**: no result.

### didActiveDeviceChanged
**Description**: Event fired when current active device has changed.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | -----------
**deviceId**  | `NSString *` | Device Id
**errorCode** | `uint32_t`   | Error code

**Result**: no result.

# AudioController Protocol
## initAudio
**Description**: call this method to open playback and record devices. It's recommended to call this method before calling to join method.

**Parameters**: N/A

**Result**: OK for successful otherwise error code.

## setConfig
**Description**: User can set audio capture and playback active devices.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
**val**   | `NSString *`               | Value
**key**   | `AudioControllerConfigKey` | Configuration option

**Result**: N/A

## getConfig
**Description**: User can receive information about active capture and playback devices.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
**key**   | `AudioControllerConfigKey` | Configuration option

**Result**: value of chosen configuration.

## isPlaybackMuted
**Description**: Get playback current state (mute/unmute)

**Parameters**: no parameters.

**Result**: true for mute otherwise unmute.

## setPlaybackMute
**Description**: Set playback current state.

**Parameters**:

Attribute       | Type   | Requirements | Description
--------------- | ------ | ------------ | ----------------------------------------
**playEnabled** | `BOOL` | Required     | State flag TRUE for mute otherwise FALSE

**Result**: No Results.

## isRecordMuted
**Description**: Get record current state (mute/unmute)

**Parameters**: no parameters.

**Result**: true for mute otherwise unmute.

## setRecordMute
**Description**: Set recorder current state.

**Parameters**:

Attribute         | Type   | Requirements | Description
----------------- | ------ | ------------ | ----------------------------------------
**recordEnabled** | `BOOL` | Required     | State flag TRUE for mute otherwise FALSE

**Result**: no result.

## getRecorderDevicesList
**Description**: Get list of connected microphone devices.

**Parameters**: N/A

**Result**: NSArray * array. The array holds the current connected microphone devices.

## getPlaybackDevicesList
**Description**: Get list of connected speaker devices.

**Parameters**: N/A

**Result**: NSArray * array. The array holds the current connected speaker devices.

## Properties
### delegate
**Description**: sdk user must set id<AudioControllerDelegate> in order to receive completion events of AudioContoller methods such as join, leave...

**Parameters**:

Attribute    | Type                      | Description
------------ | ------------------------- | --------------------------------------------------------------
**delegate** | `VideoControllerDelegate` | user object, which implements VideoControllerDelegate protocol

### MicVolume
**Description**: Property to get/set the volume of the microphone.

### SpeakerVolume
**Description**: Property to get/set the volume of the speakers.

## AudioControllerDelegate
### didAudioTransmitStateChanged
**Description**: Event fired when audio transmit state was changed.

**Parameters**:

Attribute     | Type     | Description
------------- | -------- | ------------------------
**state**     | `BOOL`   | Audio transmit new state
**errorCode** | uint32_t | Error code

**Result**: no result.

### didAudioReceiveStateChanged
**Description**: Event fired when audio receive state was changed.

Parameters:

Attribute     | Type     | Description
------------- | -------- | -----------------------
**state**     | `BOOL`   | Audio receive new state
**errorCode** | uint32_t | Error code

**Result**: no result.

### didActiveDeviceChanged
**Description**: Event fired when current active device has changed.

**Parameters**:

Attribute      | Type              | Description
-------------- | ----------------- | ---------------------------
**deviceType** | `MediaDeviceType` | Recorder or playback device
**deviceId**   | `NSString *`      | Device Id
**errorCode**  | `uint32_t`        | Error code

**Result**: no result.

### didAudioDeviceStateChanged
**Description**: Event fired when audio device power is changed.

**Parameters**:

Attribute      | Type              | Description
-------------- | ----------------- | ------------------------------
**deviceId**   | `NSString *`      | Device Id
**deviceType** | `MediaDeviceType` | Recorder or playback device
**state**      | `BOOL`            | True for open otherwise closed
**errorCode**  | `uint32_t`        | Error code

**Result**: no result.

## AudioControllerConfigKey
The enum of configuration keys:
- AudioRenderDeviceId
- AudioCaptureDeviceId

# Effect Protocol
## Properties
### effectName
**Description**: read only property. Effect name.

**Result**: Return effect name.

### effectId
**Description**: read only property. Effect id.

**Result**: Return effect id.

### iconUrl
**Description**: read only property. Icon URL.

**Parameters**: N/A

**Result**: Return icon URL.

## VideoConfigKey
The enum of configuration keys: kCaptureDeviceId, kResolution, kFps, kEffectId

# Device Protocol
## Properties
## deviceName
**Description**: read only property. Device name.

**Result**: Return device name.

## deviceId
**Description**: read only property. Effect id.

**Result**: Return device id.

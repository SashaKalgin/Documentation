#iOS API Guide

Table Of Contents
<!-- TOC depth:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [iOS API Guide](#ios-api-guide)
- [ooVooClient Interface](#oovooclient-interface)
	- [sharedInstance](#sharedinstance)
	- [setLogger](#setlogger)
	- [setLogLevel](#setloglevel)
	- [applicationDidEnterBackground](#applicationDidEnterBackground)
	- [applicationWillResignActive](#applicationWillResignActive)
	- [applicationWillEnterForeground](#applicationWillEnterForeground)
	- [applicationDidBecomeActive](#applicationDidBecomeActive)
	- [setClientVersion](#setclientversion)
	- [authorizeClient](#authorizeclient)
	- [getSdkVersion](#getsdkversion)
	- [updateConfig](#updateconfig)
	- [Properties](#properties)
		- [setSslVerifyPeer](#setsslverifypeer)
		- [isSslVerifyPeer](#issslverifypeer)
		- [IsAuthorized](#isauthorized)
		- [app_token](#app_token)
		- [Account](#account)
		- [AVChat](#avchat)
		- [PushService](#pushservice)
		- [Messaging](#messaging)
- [ooVooClientLogger Protocol](#oovooclientlogger-protocol)
	- [onLog](#onlog)
- [ooVooAccount Protocol](#oovooaccount-protocol)
	- [login](#login)
	- [logout](#logout)
	- [Properties](#properties)
		- [delegate](#delegate)
		- [uid](#uid)
		- [state](#state)
	- [ooVooAccountDelegate Protocol](#oovooaccountdelegate-protocol)
		- [didAccountLogIn](#didaccountlogin)
		- [didAccountLogOut](#didaccountlogout)
- [ooVooAVChat Protocol](#oovooavchat-protocol)
	- [join](#join)
	- [leave](#leave)
	- [sendData](#senddata)
	- [sendData](#senddata)
	- [registerPlugin](#registerplugin)
	- [unregisterPlugin](#unregisterplugin)
	- [isResolutionSupported](#isresolutionsupported)
	- [Properties](#properties)
		- [VideoController](#videocontroller)
		- [AudioController](#audiocontroller)
		- [isDataChannelPermit ](#isdatachannelpermit )
		- [delegate](#delegate)
	- [ooVooAVChatDelegate](#oovooavchatdelegate)
		- [didParticipantJoin](#didparticipantjoin)
		- [didParticipantLeave](#didparticipantleave)
		- [didConferenceStateChanged](#didconferencestatechanged)
		- [didReceiveData](#didreceivedata)
		- [didConferenceError](#didconferenceerror)
		- [didNetworkReliabilityChange](#didnetworkreliabilitychange)
		- [didSecurityState](#didsecuritystate)
- [ooVooVideoController Protocol](#oovoovideocontroller-protocol)
	- [setConfig](#setconfig)
	- [getConfig](#getconfig)
	- [getDevicesList](#getdeviceslist)
	- [getEffectsList](#geteffectslist)
	- [bindVideoRender](#bindvideorender)
	- [unbindVideoRender](#unbindvideorender)
	- [registerRemoteVideo](#registerremotevideo)
	- [unregisterRemoteVideo](#unregisterremotevideo)
	- [startTransmitVideo](#starttransmitvideo)
	- [stopTransmitVideo](#stoptransmitvideo)
	- [isVideoTransmited](#isvideotransmited)
	- [openCamera](#opencamera)
	- [closeCamera](#closecamera)
	- [openPreview](#openpreview)
	- [closePreview](#closepreview)
	- [sizeToCameraResolutionLevel](#sizetocameraresolutionlevel)
	- [Properties](#properties)
		- [getActiveDevice](#getactivedevice)
		- [setActiveDevice](#setactivedevice)
		- [delegate](#delegate)
	- [ooVooVideoControllerDelegate Protocol](#oovooVideoControllerdelegate-protocol)
		- [didCameraStateChanged](#didcamerastatechanged)
		- [didVideoTransmitStateChanged](#didvideotransmitstatechanged)
		- [didRemoteVideoStateChanged](#didremotevideostatechanged)
		- [didVideoPreviewStateChanged](#didvideopreviewstatechanged)
- [ooVooAudioController Protocol](#oovooaudiocontroller-protocol)
	- [initAudio](#initaudio)
	- [unInitAudio](#uninitaudio)
	- [setConfig](#setconfig)
	- [getConfig](#getconfig)
	- [isPlaybackMuted](#isplaybackmuted)
	- [setPlaybackMute](#setplaybackmute)
	- [isRecordMuted](#isrecordmuted)
	- [setRecordMuted](#setrecordmuted)
	- [hold](#hold)
	- [unhold](#unhold)
	- [Properties](#properties)
		- [delegate](#delegate)
	- [ooVooAudioControllerDelegate](#oovooaudiocontrollerdelegate)
		- [didAudioTransmitStateChange](#didaudiotransmitstatechange)
		- [didAudioReceiveStateChange](#didaudioreceivestatechange)
- [ooVooEffect Protocol](#oovooeffect-protocol)
	- [Properties](#properties)
		- [effectName](#effectname)
		- [effectID](#effectid)
		- [iconUrl](#iconurl)
		- [category](#category)
		- [purchaseID](#purchaseid)
- [ooVooDevice Protocol](#oovoodevice-protocol)
	- [Properties](#properties)
		- [deviceName](#devicename)
		- [deviceID](#deviceid)
- [ooVooVideoDevice Protocol](#oovoovideodevice)
	- [isResolutionSupported](#isresolutionsupported)
	- [isFront](#isfront)
	- [getAvailableResolutions](#getavailableresolutions)
- [ooVooParticipant Protocol](#oovooparticipant-protocol)
	- [Properties](#properties)
		- [participantID](#participantid)
		- [type](#type)
- [ooVooVideoData Protocol](#oovoovideodata)
	- [getPlane](#getplane)
	- [getPlanePitch](#getplanepitch)
	- [Property](#property)
		- [data](#data)
		- [dataLength](#datalength)
		- [width](#width)
		- [height](#height)
		- [colorFormat](#colorformat)
		- [planeCount](#planecount)
- [ooVooVideoFrame Protocol](#oovoovideoframe)
	- [Property](#property)
		- [videoData](#videodata)
		- [width](#width)
		- [height](#height)
		- [frameNumber](#framenumber)
		- [isKeyFrame](#iskeyframe)
		- [isMirror](#ismirror)
		- [rotationAngle](#rotationangle)
		- [deviceRotationAngle](#devicerotationangle)
		- [colorFormat](#colorformat)
- [ooVooVideoRender Protocol](#oovoovideorender)
	- [onProcessVideoFrame](#onprocessvideoframe)
- [ooVooPushService Protocol](#oovoopushservice)
	- [subscribe](#subscribe)
	- [unSubscribe](#unsubscribe)
	- [sendPushMessage](#sendpushmessage)
- [ooVooPushNotificationMessage Interface](#oovoopushnotificationmessage)
	- [initMessageWithArrayUsers](#initmessagewitharrayusers)
	- [Property](#property)
		- [get_to](#get_to)
		- [get_body](#get_body)
		- [get_property](#get_property)
		- [get_messageId](#get_messageId)		
- [ooVooMessaging Protocol](#oovoomessaging)
	- [sendMessage](#sendmessage)
	- [sendAcknowledgement](#sendacknowledgement)
	- [connect](#connect)
	- [disconnect](#disconnect)
	- [isConnected](#isconnected)
	- [Property](#property)
		- [delegate](#delegate)
- [ooVooMessagingDelegate Protocol](#oovoomessagingdelegate)
	- [didMessageReceive](#didmessagereceive)
	- [didMessageReceiveAcknowledgement](#didmessagereceiveacknowledgement)
	- [didConnectivityStateChange](#didconnectivitystatechange)
- [ooVooMessage Interface](#oovoomessage)
	- [initMessage](#initmessage)
	- [initMessageWithData](#initmessagewithdata)
	- [initMessageWithArrayUsers](#initmessagewitharrayusers)
	- [Property](#property)
		- [get_from](#get_from)
		- [get_to](#get_to)
		- [get_body](#get_body)
		- [get_messageId](#get_messageId)
		- [get_timestamp](#get_timestamp)
- [Enumerators](#enumerators)
	- [ooVooDeviceState](#oovoodevicestate)
	- [ooVooAudioRouteType](#oovooaudioroutetype)
	- [ooVooVideoControllerConfigKey](#oovoovideocontrollerconfigkey)
	- [ResolutionLevel](#resolutionlevel)
	- [ooVooPstnState](#oovoopstnstate)
	- [ooVooAudioControllerConfigKey](#oovooaudiocontrollerconfigkey)
	- [ooVooAVChatState](#oovooavchatstate)
	- [ooVooAVChatRemoteVideoState](#oovooavchatremotevideostate)
	- [ooVooAVParticipantType](#oovooavparticipanttype)
	- [ooVooColorFormat](#oovoocolorformat)
	- [ooVooMessageAcknowledgeState](#oovooMessageacknowledgestate)
	- [ooVooMessagingConnectivityState](#oovoomessagingconnectivitystate)

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

## applicationDidEnterBackground
**Description**: Application must call this for correct work camera and video drawing.

**Parameters**: no parameters.

**Result**: no result.


## applicationWillResignActive
**Description**: Application must call this for correct work camera and video drawing.

**Parameters**: no parameters.

**Result**: no result.

## applicationWillEnterForeground
**Description**: Application must call this for correct work camera and video drawing.

**Parameters**: no parameters.

**Result**: no result.

## applicationDidBecomeActive
**Description**: Application must call this for correct work camera and video drawing.

**Parameters**: no parameters.

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

## getSdkVersion
**Description**: the method allows to get current version of SDK.

**Parameters**: N/A

**Result**: return string SDK version.

## updateConfig
**Description**: Use this method to update config list.

**Parameters**:

Attribute | Type       | Requirements | Description
--------- | ---------- | ------------ | ------------------------------------------------
completion | `CompletionHandler` | Required     | The handler notifies about operation completion .

**Result**: no result.

## Properties

### setSslVerifyPeer
**Description**: the property allows to set SSL verification.

**Parameters**:

Attribute 		| Type         | Requirements | Description
------------- | ------------ | ------------ | ---------------------------------
sslVerifyPeer |`BOOL`  			 | Required    	| Define SSL verification.

**Result**: no parameters.

### isSslVerifyPeer
**Description**: the property allows to check, if performed SSL verification.

**Parameters**: no parameters.

**Result**: boolean value, true when performed SSL verification.

### IsAuthorized
**Description**: atomic and read only property. Return if current client is authorized.

**Parameters**: no parameters.

**Result**: authorization status: true for yes otherwise false.

### app_token

**Description**: atomic and read only property. The application token received from web site.

**Parameters**: no parameters.

**Result**: string of application token.

### Account
**Description**: Get read only ooVoo client account property. Use account object to perform operations such as: login, logout.

**Parameters**: N/A.

**Result**: returns reference to object that implements Account protocol.

### AVChat
**Description**: Get read only ooVoo audio video property. Use AVChat to perform operation such as: join, leave conference.

**Parameters**: N/A.

**Result**: returns reference to object that implements AVChat protocol.

### PushService
**Description**: Get read only push service property. Use PushService to perform operation such as: sendPushMessage, subscribe ...

**Parameters**: N/A.

**Result**: returns reference to object that implements PushService protocol.

### Messaging
**Description**: Get read only messaging property. Use Messaging to perform operation such as: send, sendAcknowledgement ...

**Parameters**: N/A.

**Result**: returns reference to object that implements Messaging protocol.


# ooVooClientLogger Protocol
## onLog
**Description**: call back function that should handle the log from SDK.

**Parameters**:

Attribute | Type         | Requirements | Description
--------- | ------------ | ------------ | ---------------------------------
Level     | LogLevel     | Required     | The log level, error, debug, info
Log       | `NSString *` | Required     | Answer result callback

**Result**: N/A

# ooVooAccount Protocol
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

### delegate
**Description**: sdk user must set id<ooVooAccountDelegate> in order to receive completion events of ooVooAccount methods such as login, loguot.

**Parameters**:

Attribute    | Type             			| Description
------------ | ---------------------- | -----------------------------------------------------
**delegate** | `ooVooAccountDelegate` | user object, which implements ooVooAccountDelegate protocol

**Result**: N/A

### uid
**Description**: read only property which returns account id.

**Parameters**: no parameters

**Result**: account id.

### state
**Description**: read only property which returns account login state.

**Parameters**: no parameters

**Result**: Returns the status of user, Login or Logout.

## ooVooAccountDelegate Protocol

### didAccountLogIn
**Description**: Event occurs when user performs login.

**Parameters**:

Attribute    | Type         | Description
------------ | ------------ | -----------
**account**      | `ooVooAccount` | This protocol of ooVooAccount.

**Result**: No Results

### didAccountLogOut
**Description**: Event occurs when user performs logout.

**Parameters**:

Attribute    | Type         | Description
------------ | ------------ | -----------
**account**      | `ooVooAccount` | This protocol of ooVooAccount.

**Result**: No Results

# ooVooAVChat Protocol
## join
**Description**: Join conference call.

**Parameters**:

Attribute | Type         | Description
--------- | ------------ | -------------
**cid**   | `NSString *` | Conference id
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

## registerPlugin
**Description**: The method allows to register a custom plugin in ooVoo SDK.

**Parameters**:

Attribute     | Type                 | Description
--------------| -------------------- | ------------------------
**plugin**    | `ooVooPluginFactory` | Plugin for registration.
**completion**| `CompletionHandler`  | Completion handler for receive result of register plugin

**Result**: no result

## unregisterPlugin
**Description**: The method allows you to cancel the custom plugin in ooVoo SDK.

**Parameters**:

Attribute  | Type         | Description
---------- | ------------ | ------------------------
**plugin** | `ooVooPluginFactory` | Plugin for unregistration.

**Result**: no result


## isResolutionSupported
**Description**: The method allows to check supporting the resolution in AVChat.

**Parameters**:

Attribute        | Type              				| Description
---------------- | ------------------------ | ------------------------------
**resolution**   | `ResolutionLevel`        | This is a level of resolution.

**Result**: Returns boolean value, if supported by the requested resolution.

## Properties
### VideoController
**Description** Get read only video controller property. Use video controller to perform operations such as: open camera, open preview....

**Parameters**: N/A

**Result**: returns reference to object that implements ooVooVideoController protocol.

### AudioController
**Description**: Get read only audio controller property. Use video controller to perform operations such as: open mute speaker/microphone, get device list...

**Parameters**: N/A

**Result**: returns reference to object that implements ooVooAudioController protocol.

### isDataChannelPermit
**Description**: Get read only in call message permit property. Used for perform check the permission.

**Parameters**: N/A

**Result**: returns boolean value.

### delegate
**Description**: sdk user must set id<ooVooAVChatDelegate> in order to receive completion events of AVChat methods such as join, leave...

**Parameters**:

Attribute    | Type             | Description
------------ | ---------------- | -----------------------------------------------------
**delegate** | `ooVooAVChatDelegate` | user object, which implements ooVooAVChatDelegate protocol

**Result**: N/A

## ooVooAVChatDelegate
### didParticipantJoin
**Description**: Event occurs when participant joined conference.

**Parameters**:

Attribute    | Type         | Description
------------ | ------------ | -----------
**participant**      | `ooVooParticipant` | This participant added to conference.
**user_data** | `NSString *` | User data

**Result**: No Results

### didParticipantLeave
**Description**: Event occurs when participant leave conference.

**Parameters**:

Attribute    | Type         | Description
------------ | ------------ | -----------
**participant**      | `ooVooParticipant` |  This participant is disconnected from the conference.


**Result**: No Results

### didConferenceStateChanged
**Description**: Event occurs when user joined or disconnected from conference.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | ------------------------------------------------
**state**     | `ooVooAVChatState` | Enumerator which indicates conference new state.
**code** 			| `sdk_error` | Conference error code

**Result**: No Results

### didReceiveData
**Description**: Event occurs when user receive data from remote participants.

**Parameters**:

Attribute | Type         | Description
--------- | ------------ | -----------
**uid**   | `NSString *` | User id
**data**  | `NSData*`    | message

### didConferenceError
**Description**: Event occurs when conference error is received.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | ------------------------------------------------
**code** 			| `sdk_error`  | Conference error code

**Result**: No Results

### didNetworkReliabilityChange
**Description**: Event occurs when network reliability change.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | ------------------------------------------------
**scope** 			| `NSString *`  | A number from 1-4, 1 indicate that network is worse 4 network is best.

**Result**: No Results

### didSecurityState
**Description**: Event occurs when user changed security  mode.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | ------------------------------------------------
**is_secure** 			| `bool`  | true for secured otherwise false.

**Result**: No Results

# ooVooVideoController Protocol
## setConfig
**Description**: User can set configuration of the following: capture device, resolution, FPS, effect.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
**val**   | `NSString *`               | value
**key**   | `ooVooVideoControllerConfigKey` | Configuration option

**Result**: N/A

## getConfig
**Description**: User can find configuration of the following: capture device, resolution, FPS, effect.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
**key**   | `ooVooVideoControllerConfigKey` | Configuration option

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

## isVideoTransmited
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

## sizeToCameraResolutionLevel
**Description**: the method allows to define the resolution level of video.

**Parameters**:

Attribute 	| Type                       | Description
----------- | -------------------------- | --------------------
**width**   | `int`      								 | This width of video.
**height**  | `int`     								 | This height of video.

**Result**: matches the resolution level to the width and the height.

## Properties
## getActiveDevice
**Description**: Get the current active video camera.

**Parameters**: N/A

**Result**: Device/camera object. The object holds the current active video camera.

## setActiveDevice
**Description**: the method allows to set the active camera.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
**device**   | `ooVooVideoDevice`      | The active camera.

**Result**: N/A

### delegate
**Description**: sdk user must set id<ooVooVideoControllerDelegate> in order to receive completion events of ooVooVideoController methods such as join, leave...

**Parameters**:

Attribute    | Type                      | Description
------------ | ------------------------- | -----------------------------
**delegate** | `ooVooVideoControllerDelegate` | user object, which implements | ooVooVideoControllerDelegate protocol

**Result**: N/A

## ooVooVideoControllerDelegate Protocol
### didCameraStateChange
**Description**: Event fired when system detects that camera state was changed.

**Parameters**:

Attribute     | Type       | Description
------------- | ---------- | ----------------
**state**     | `ooVooDeviceState`     | Camera new state
**devId**     | `NSString *` | Device ID
**width**     | `const int`  | This width of video.
**height**    | `const int`  | This height of video.
**fps**     	| `const int`  | This Frame Per Second of video.
**code** 			| `sdk_error` | Error code

**Result**: no result.

### didVideoTransmitStateChange
**Description**: Event fired when video transmit state was changed.

**Parameters**:

Attribute     | Type       | Description
------------- | ---------- | ------------------------
**state**     | `BOOL`     | Video transmit new state
**devId**     | `NSString *` | Device ID
**code** 			| `sdk_error` | Error code

**Result**: no result.

### didRemoteVideoStateChange
**Description**: Event fired when remote user video transmit state was changed.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | ------------------------
**uid**       | `NSString *` | Remote user id
**state**     | `ooVooAVChatRemoteVideoState`       | Video transmit new state
**width**     | `const int`  | This width of video.
**height**    | `const int`  | This height of video.
**code** 			| `sdk_error`  | Error code

**Result**: no result.

### didVideoPreviewStateChange
**Description**: Event fired when preview video state was changed.

**Parameters**:

Attribute     | Type       | Description
------------- | ---------- | ------------------------
**state**     | `BOOL`     | Video transmit new state
**devId**     | `NSString *` | Device ID
**code** 			| `sdk_error` | Error code

**Result**: no result.

# ooVooAudioController Protocol
## initAudio
**Description**: call this method to open playback and record devices. It's recommended to call this method before calling "join" the method.

**Parameters**: N/A

**Result**: OK for successful otherwise error code.

## unInitAudio
**Description**: call this method to close playback and stop record devices. It's recommended to call this method before calling "leave" the method.

**Parameters**: N/A

**Result**: OK for successful otherwise error code.

## setConfig
**Description**: User can set audio capture and playback active devices.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
**val**   | `NSString *`               | Value
**key**   | `ooVooAudioControllerConfigKey` | Configuration option

**Result**: N/A

## getConfig
**Description**: User can receive information about active capture and playback devices.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
**key**   | `ooVooAudioControllerConfigKey` | Configuration option

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

## setRecordMuted
**Description**: Set recorder current state.

**Parameters**:

Attribute         | Type   | Requirements | Description
----------------- | ------ | ------------ | ----------------------------------------
**recordEnabled** | `BOOL` | Required     | State flag TRUE for mute otherwise FALSE

**Result**: no result.

## hold
**Description**: The method allows to set the mode on hold.

**Parameters**: N/A

**Result**: N/A.

## unhold
**Description**: The method allows to set the mode unhold.

**Parameters**: N/A

**Result**: N/A.

## Properties

### delegate
**Description**: sdk user must set id<ooVooAudioControllerDelegate> in order to receive completion events of AudioContoller methods such as join, leave...

**Parameters**:

Attribute    | Type                      | Description
------------ | ------------------------- | --------------------------------------------------------------
**delegate** | `ooVooAudioControllerDelegate` | user object, which implements ooVooAudioControllerDelegate protocol

## ooVooAudioControllerDelegate
### didAudioTransmitStateChanged
**Description**: Event fired when audio transmit state was changed.

**Parameters**:

Attribute     | Type     | Description
------------- | -------- | ------------------------
**state**     | `BOOL`   | Audio transmit new state
**code** 			| `sdk_error` | Error code

**Result**: no result.

### didAudioReceiveStateChanged
**Description**: Event fired when audio receive state was changed.

Parameters:

Attribute     | Type     | Description
------------- | -------- | -----------------------
**state**     | `BOOL`   | Audio receive new state
**code** 			| `sdk_error` | Error code

**Result**: no result.

# ooVooEffect Protocol
## Properties
### effectName
**Description**: read only property. Effect name.

**Result**: Return effect name.

### effectID
**Description**: read only property. Effect id.

**Result**: Return effect id.

### iconUrl
**Description**: read only property. Icon URL.

**Parameters**: N/A

**Result**: Return icon URL.

### category
**Description**: read only property. This is a type of category.

**Parameters**: N/A

**Result**: Return a type of category.

### purchaseID
**Description**: read only property. This is ID for each purchase of Effect.

**Parameters**: N/A

**Result**: Return ID of purchase.

# ooVooDevice Protocol
## Properties
## deviceName
**Description**: read only property. Device name.

**Result**: Return device name.

## deviceID
**Description**: read only property. Device id.

**Result**: Return device id.

# ooVooVideoDevice Protocol

## isResolutionSupported
**Description**: The method allows to check supporting the resolution of device.

**Parameters**:

Attribute        | Type              				| Description
---------------- | ------------------------ | ------------------------------
**resolution**   | `ResolutionLevel`        | This is a level of resolution.


**Result**: Returns boolean value, if supported by the requested resolution.

## isFront
**Description**: The method allows to check, if this is the front camera.

**Parameters**: N/A

**Result**: Returns boolean value.

## getAvailableResolutions
**Description**: The method allows to get all available resolutions.

**Parameters**: N/A

**Result**: Returns a array of available resolutions.

# ooVooParticipant Protocol
## Properties
### participantID
**Description**: read only property. Participant ID.

**Result**: Return ID of participant.

### type
**Description**: read only property. This type of participant.

**Result**: Return ooVooAVParticipatType.

# ooVooVideoData Protocol

### getPlane
**Description**:The method allows to obtain a pointer to a specific plane.

**Parameters**:

Attribute | Type 	 | Description
--------- | ------ | ---------------
**int**   | `index`| This index of plane.

**Result**: Returns a pointer of indeterminate type.

### getPlanePitch
**Description**:The method allows to obtain a pitch on a specific plane.

**Parameters**:

Attribute | Type 	 | Description
--------- | ------ | ---------------
**int**   | `index`| This index of plane.

**Result**: Returns pitch.

## Properties

### data
**Description**: read only property. The property allows to get video data.

**Result**: Return pointer of video data.

### dataLength
**Description**: read only property. The property allows to get size of video data.

**Result**: Return length of video data.

### width
**Description**: read only property. The property allows to get width of video data.

**Result**: Return width of video data.

### height
**Description**: read only property. The property allows to get height of video data.

**Result**: Return height of video data.

### colorFormat
**Description**: read only property. The property allows to get color format of video data.

**Result**: Return color format of video data.

### planeCount
**Description**: read only property. The property allows to get the number of planes.

**Result**: Return the number of planes.

# ooVooVideoFrame Protocol

## Properties

### videoData
**Description**: read only property. The property allows to get object ooVooVideoData.

**Result**: Return object of ooVooVideoData.

### width
**Description**: read only property. The property allows to get width of video frame.

**Result**: Return width of video frame.

### height
**Description**: read only property. The property allows to get height of video frame.

**Result**: Return height of video frame.

### frameNumber
**Description**: read only property. The property allows to get number to a video frame.

**Result**: Returns number to a video frame.

### isKeyFrame
**Description**: read only property. The property allows to get key to a video frame.

**Result**: Returns key to a video frame.

### isMirror
**Description**: read only property. The property allows to get BOOL value, if a video frame received in a mirror reflection.

**Result**: Returns BOOL value.

### rotationAngle
**Description**: read only property. The property allows to get rotation angle of video frame.

**Result**: Returns rotation angle in degree.

### deviceRotationAngle
**Description**: read only property. The property allows to get rotation angle of device.

**Result**: Returns rotation angle in degree.

### colorFormat
**Description**: read only property. The property allows to get color format of video frame.

**Result**: Returns enum of ooVooColorFormat.

# ooVooVideoRender Protocol

### onProcessVideoFrame
**Description**:The method allows to obtain video frame and you can process this video frame. In addition perform before coding video frame or after decoding video frame.

**Parameters**:

Attribute | Type 	 | Description
--------- | ------ | ---------------
**ooVooVideoFrame**   | `frame`| This video frame for processing.

**Result**: N/A

# ooVooPushService Protocol

### subscribe
**Description**:The method allows to subscribe on push notification events.

**Parameters**:

Attribute 		| Type 		| Description
--------------------- | ----------- | ---------------
**token**   					| `NSString *`| Device token for remote notification received on didRegisterForRemoteNotificationsWithDeviceToken and generated by UIApplication::registerForRemoteNotificationTypes method.
**deviceUid**   			| `NSString *`| Device Unique Identifiers. Can be generated once on app installation and used for all users, who are logged in with this specific device.
**completion**   			| `CompletionHandler`| The handler notifies about operation completion

**Result**: N/A

### unSubscribe
**Description**:The method allows to un-subscribe from push notification events.

**Parameters**:

Attribute 		| Type 	 	| Description
--------------------- | ----------- | ---------------
**token**   					| `NSString *`| Device token for remote notification received on didRegisterForRemoteNotificationsWithDeviceToken and generated by UIApplication::registerForRemoteNotificationTypes method.
**deviceUid**   			| `NSString *`| Device Unique Identifiers. Can be generated once on app installation and used for all users, who are logged in with this specific device.
**completion**   			| `CompletionHandler`| The handler notifies about operation completion

**Result**: N/A

### sendPushMessage
**Description**: Used for sending text messages between 3rd party users in same application.

**Parameters**:

Attribute 						| Type 	 			| Description
--------------------- | ----------- | ---------------
**message**   					| `ooVooPushNotificationMessage`| This a text message for other users.
**completion**   			| `CompletionHandler`| The handler notifies about operation completion

**Result**: N/A

# ooVooPushNotificationMessage Interface

### initMessageWithArrayUsers
**Description**: Used for sending text messages between 3rd party users in same application.

**Parameters**:

Attribute 			| Type 	 			| Description
--------------- | ----------- | ---------------
**to_list**			| `NSString *`| This a array of users, for receive a text message.
**body**   			| `NSString *`| This a body of text message.
**property**   	| `NSString *`| This a property.
**ttl**   			| `unsigned int`| This a time  in seconds afterwards the message should not be sent.

**Result**: returns instance of object.

## Properties

### get_to
**Description**: read only property. The property allows to get array of users which received a push notification.

**Result**: Return array of users.

### get_body
**Description**: read only property. The property allows to get body of message.

**Result**: Returns a body of the message.

### get_property
**Description**: read only property. The property allows to get a property.

**Result**: Returns a property.

### get_messageId
**Description**: read only property. The property allows to get ID of message.

**Result**: Returns ID of message.

# ooVooMessaging Protocol

### sendMessage
**Description**: The method allows to send text message to user(s).

**Parameters**:

Attribute 						| Type 	 			| Description
--------------------- | ----------- | ---------------
**message**   					| `ooVooMessage*`| This a text message for other users.
**completion**   			| `CompletionHandler`| The handler notifies about operation completion

**Result**: N/A

### sendAcknowledgement
**Description**: The method allows to get a status of send acknowledgement of a text message.

**Parameters**:

Attribute 						| Type 	 			| Description
--------------------- | ----------- | ---------------
**state**   					| `ooVooMessageAcknowledgeState`| This a status of acknowledgement.
**message**   					| `ooVooMessage*`| This a text message for other users.
**completion**   			| `CompletionHandler`| The handler notifies about operation completion

**Result**: N/A


### connect

The method start connect to messaging service

*Gets a parameters list:**  no parameters.

**Return a value:** no result, calback onConnectivityStateChange will fire.


### disconnect

The method start disconnect to messaging service

*Gets a parameters list:**  no parameters.

**Return a value:** no result, calback onConnectivityStateChange will fire.

### isConnected

*Gets a parameters list:**  no parameters.

**Return a value:** boolean value, true mean that sender connected to messaging service, false not connected



## Properties

### delegate
**Description**: user must set id<ooVooMessagingDelegate> in order to receive completion events of ooVooMessage.

**Parameters**:

Attribute    | Type             			| Description
------------ | ---------------------- | -----------------------------------------------------
**delegate** | `ooVooMessagingDelegate` | user object, which implements ooVooMessage protocol

**Result**: N/A

# ooVooMessagingDelegate Protocol

### didMessageReceive
**Description**: Event fired when a text message was received.

**Parameters**:

Attribute     | Type     | Description
------------- | -------- | ------------------------
**message**     | `ooVooMessage*`   | This a text message was received.

**Result**: no result.

### didMessageReceiveAcknowledgement
**Description**: Event fired when was received acknowledgement that the text a message delivered or readed by user.

**Parameters**:

Attribute     | Type     | Description
------------- | -------- | ------------------------
**state**     | `ooVooMessageAcknowledgeState`   | This a text message was received.
**messageId**     | `NSString*`   | This ID of message.

**Result**: no result.


### didConnectivityStateChange
**Description**: Event fired when was  connectivity state was changed.

**Parameters**:

Attribute     | Type     | Description
------------- | -------- | ------------------------
**state**     | `ooVooMessageConnectivityState`   | This a connectivity state.
**error**     | `sdk_error`   | The error code.
**description** |`NSString*`| The event desciption, can be null

**Result**: no result.

# ooVooMessage Interface

### initMessage
**Description**:The method allows to initialize the ooVooMessage.

**Parameters**:

Attribute 						| Type 	 			| Description
--------------------- | ----------- | ---------------
**to**   					| `NSString *`| The user, who will be sent a text message.
**message**   			| `NSString *`| This a text message.

**Result**: returns instance of object.

### initMessageWithData
**Description**:The method allows to initialize the ooVooMessage.

**Parameters**:

Attribute 						| Type 	 			| Description
--------------------- | ----------- | ---------------
**to**   					| `NSArray*`| The user(s), who will be sent this a text message.
**message**   			| `NSData *`| This is a test message in a binary format.

**Result**: returns instance of object.

### initMessageWithArrayUsers
**Description**:The method allows to initialize the ooVooMessage.

**Parameters**:

Attribute 						| Type 	 			| Description
--------------------- | ----------- | ---------------
**to**   					| `NSArray*`| The user(s), who will be sent this a text message.
**message**   			| `NSString *`| This a text message.

**Result**: returns instance of object.

## Properties

### get_from
**Description**: read only property. The property allows to get user ID who send a message.

**Result**: Returns user ID.

### get_to
**Description**: read only property. The property allows to get array of users which received a push notification.

**Result**: Return array of users.

### get_body
**Description**: read only property. The property allows to get body of message.

**Result**: Returns a body of the message.

### get_messageId
**Description**: read only property. The property allows to get ID of message.

**Result**: Returns ID of message.

### get_timestamp
**Description**: read only property. The property allows to get a time last operation with a message.

**Result**: Returns time.


# Enumerators
### ooVooDeviceState
	The enum used in the method didCameraStateChange :
	ooVooNotCreated, ooVooTurningOn, ooVooTurnedOn, ooVooTurningOff, ooVooTurnedOff, ooVooRestarting, ooVooOnHold.

### ooVooAudioRouteType
	The enum used for define an audio route :
	ooVooAudiotoEarpiece, ooVooAudioRouteToHeadphone, ooVooAudioRouteToBluetooth, ooVooAudioRouteToSpeaker

### ooVooVideoControllerConfigKey
	The enum used in the methods setConfig/getConfig for define configuration of video :
	 ooVooVideoControllerConfigKeyCaptureDeviceId, ooVooVideoControllerConfigKeyResolution, ooVooVideoControllerConfigKeyFps, ooVooVideoControllerConfigKeyEffectId

### ResolutionLevel
	The enum used in the methods isResolutionSupported/sizeToCameraResolutionLevel for define resolution of video :
	ResolutionLevelNotSpecified, ResolutionLevelLow, ResolutionLevelMed, ResolutionLevelHigh, ResolutionLevelHD

### ooVooPstnState
	The enum used in the method didPhonePstnCallStateChange for define status of call :
	 ooVooPstnStateStartCall, ooVooPstnStateEndCall, ooVooPstnStateInProgress, ooVooPstnStateRinging, ooVooPstnStateCallIsBeingForwarded, ooVooPstnStateQueued, ooVooPstnStateSessionInProgress, ooVooPstnStateOK, ooVooPstnStateBadRequest, ooVooPstnStatePaymentRequired, ooVooPstnStateNotFound, ooVooPstnStateRequestTimedOut, ooVooPstnStateConnectionTimedOut, ooVooPstnStateTooManyPstnClients, ooVooPstnStateInvalidPhoneNumber, ooVooPstnStateInfrastructureError

### ooVooAudioControllerConfigKey
	The enum used in the methods setConfig/getConfig for define configuration of audio :
	 ooVooAudioControllerConfigKeyRenderDeviceId, ooVooAudioControllerConfigKeyCaptureDeviceId, ooVooAudioControllerConfigKeyAudioSetMode

### ooVooAVChatState
	The enum used in the method didConferenceStateChange for define status of AVChat :
	 ooVooAVChatStateJoined, ooVooAVChatStateDisconnected

## ooVooAVChatRemoteVideoState
	The enum used in the method didRemoteVideoStateChange for define when remote video state has changed :
	 ooVooAVChatRemoteVideoStateStated, ooVooAVChatRemoteVideoStateStopped, ooVooAVChatRemoteVideoStatePaused, ooVooAVChatRemoteVideoStateResumed

## ooVooAVParticipantType
	The enum used in the property ooVooAVParticipantType for define the type of participant :
	 ooVooAVParticipantTypeVOIP, ooVooAVParticipantTypePSTN

## ooVooColorFormat
This enum type is a special data type that enables define about existing color formats :
 ooVooColorFormatNONE - (value -1), ooVooColorFormatYV12 - (value 100) Planar Y, V, U (4:2:0) (note V,U order!), ooVooColorFormatNV12 - Planar Y, merged U->V (4:2:0), ooVooColorFormatNV21 -       // Planar Y, merged V->U (4:2:0) (note V,U order!), ooVooColorFormatYUY2 - Composite Y->U->Y->V (4:2:2), ooVooColorFormatUYVY - Composite U->Y->V->Y (4:2:2), ooVooColorFormatYUV420 - Planar Y, U, V, ooVooColorFormatRGB32 - Composite R->G->B->A, ooVooColorFormatRGB24 - Composite R->G->B, ooVooColorFormatBGR32 - Composite B->G->R->A, ooVooColorFormatBGR24 - Composite B->G->R, ooVooColorFormatGRAY - Luminance component only, ooVooColorFormatYUV420A - Planar Y, U, V, Alpha, ooVooColorFormatYUV444A - Planar Y, U, V, Alpha, ooVooColorFormatGRAYA - Luminance with Alpha, ooVooColorFormatSURFACE - GPU surface, ooVooColorFormatRAW - Raw data (internal format)N


## ooVooMessageAcknowledgeState
This enum type is a special data type that enables define about existing message acknowledge state:
Delivered - marks, that message was delivered to recipient, Read - marks, that message was read by recipient.

## ooVooMessagingConnectivityState
This enum type is a special data type for connectivity events:
Connected - marks, that sender connected to messaging service, Disconnected - marks, that sender disconnected from messaging service

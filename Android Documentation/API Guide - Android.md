#Android API Guide

Table of Contents

<!-- TOC depth:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Android API Guide](#android-api-guide)
- [Classes](#classes)
- [ooVooClient](#oovooclient)
	- [Constructor](#constructor)
	- [sharedInstance](#sharedinstance)
	- [getAccount](#getaccount)
	- [getAVChat](#getavchat)
	- [isAuthorized](#isauthorized)
	- [isDeviceSupported](#isdevicesupported)
	- [setContext](#setcontext)
	- [isTablet](#istablet)
	- [setSslPeerVerify](#setsslpeerverify)
	- [isSslPeerVerify](#issslpeerverify)
	- [authorizeClient](#authorizeclient)
	- [setLogger](#setlogger)
	- [setLogLevel](#setloglevel)
	- [getSdkVersion](#getsdkversion)
	- [updateConfig](#updateconfig)
- [JNIObject](#jniobject)
	- [isValid](#isvalid)
	- [release](#release)
- [Account](#account)
	- [login](#login)
	- [getID](#getid)
	- [logout](#logout)
- [Device](#device)
	- [getID](#getid)
	- [getName](#getname)
- [Effect](#effect)
	- [getCategory](#getcategory)
	- [getIconUrl](#geticonurl)
	- [getID](#getid)
	- [getName](#getname)
	- [getPurchaseId](#getpurchaseid)
- [PluginFactory](#pluginfactory)
	- [createPluginInstance](#createplugininstance)
- [ooVooSdkResultListener](#oovoosdkresultlistener)
	- [onResult](#onresult)
- [ooVooSdkResult](#oovoosdkresult)
	- [getResult](#getresult)
	- [getDescription](#getdescription)
	- [getUserInfo](#getuserinfo)
- [LoggerListener](#loggerlistener)
	- [LogLevel](#loglevel)
	- [fromInt](#fromint)
	- [levelToInt](#leveltoint)
	- [fromString](#fromstring)
	- [OnLog](#onlog)
- [AVChat](#avchat)
	- [ConferenceState](#conferencestate)
	- [setListener](#setlistener)
	- [join](#join)
	- [leave](#leave)
	- [send](#send)
	- [send](#send)
	- [registerPlugin](#registerplugin)
	- [unregisterPlugin](#unregisterplugin)
	- [isInCallMessagesPermit](#isincallmessagespermit)
	- [getAvailableResolutions](#getavailableresolutions)
	- [isResolutionSupported](#isresolutionsupported)
	- [getVideoController](#getvideocontroller)
	- [getAudioController](#getaudiocontroller)
	- [AVChatListener](#avchatlistener)
		- [onParticipantJoined](#onparticipantjoined)
		- [onParticipantLeft](#onparticipantleft)
		- [onConferenceStateChanged](#onconferencestatechanged)
		- [onReceiveData](#onreceivedata)
		- [onConferenceError](#onconferenceerror)
		- [onNetworkReliability](#onnetworkreliability)
- [Participant](#participant)
	- [ParticipantType](#participanttype)
	- [getID](#getid)
	- [getType](#gettype)
- [AudioController](#audiocontroller)
	- [AudioRouteMode](#audioroutemode)
	- [setListener](#setlistener)
	- [initAudio](#initaudio)
	- [uninitAudio](#uninitaudio)
	- [isPlaybackMuted](#isplaybackmuted)
	- [isRecordMuted](#isrecordmuted)
	- [setRecordMuted](#setrecordmuted)
	- [setPlaybackMuted](#setplaybackmuted)
	- [getAudioRouteController](#getaudioroutecontroller)
	- [setAudioRouteMode](#setaudioroutemode)
	- [AudioControllerListener](#audiocontrollerlistener)
		- [onAudioTransmitStateChanged](#onaudiotransmitstatechanged)
		- [onAudioReceiveStateChanged](#onaudioreceivestatechanged)
		- [onMicrophoneStateChange](#onmicrophonestatechange)
		- [onSpeakerStateChange](#onspeakerstatechange)
- [AudioRoute](#audioroute)
	- [getName](#getname)
	- [getRouteId](#getrouteid)
	- [isActive](#isactive)
- [AudioRouteController](#audioroutecontroller)
	- [getRoutes](#getroutes)
	- [setListener](#setlistener)
	- [setRoute](#setRoute)
	- [AudioRouteControllerListener](#audioroutecontrollerlistener)
		- [onAudioRouteChanged](#onaudioroutechanged)
- [VideoController](#videocontroller)
	- [ResolutionLevel](#resolutionlevel)
	- [VideoConfigKey](#videoconfigkey)
	- [getConfig](#getconfig)
	- [setConfig](#setconfig)
	- [setListener](#setlistener)
	- [setActiveResolution](#setactiveresolution)
	- [getActiveResolution](#getactiveresolution)
	- [setFps](#setfps)
	- [getFps](#getfps)
	- [setActiveEffect](#setactiveeffect)
	- [getActiveEffect](#getactiveeffect)
	- [setActiveDevice](#setactivedevice)
	- [getActiveDevice](#getactivedevice)
	- [openPreview](#openpreview)
	- [closePreview](#closepreview)
	- [openCamera](#opencamera)
	- [closeCamera](#closecamera)
	- [startTransmit](#starttransmit)
	- [stopTransmit](#stoptransmit)
	- [isTransmited](#istransmited)
	- [bindRender](#bindrender)
	- [unbindRender](#unbindrender)
	- [registerRemote](#registerremote)
	- [unregisterRemote](#unregisterremote)
	- [getDeviceList](#getdevicelist)
	- [getEffectList](#geteffectlist)
	- [sizeToResolutionLevel](#sizetoresolutionlevel)
	- [VideoControllerListener](#videocontrollerlistener)
		- [RemoteVideoState](#remotevideostate)
		- [onRemoteVideoStateChanged](#onremotevideostatechanged)
		- [onCameraStateChanged](#oncamerastatechanged)
		- [onTransmitStateChanged](#ontransmitstatechanged)
		- [onVideoPreviewStateChanged](#onvideopreviewstatechanged)
		- [onCameraChanged](#oncamerachanged)
- [VideoDevice](#videodevice)
	- [getAvailableResolutions](#getavailableresolutions)
	- [isResolutionSupported](#isresolutionsupported)

<!-- /TOC -->

# ooVooClient
## Constructor
Constructor ooVooClient which implements two modules the account and the avchat.

**Gets a parameters list:** without parameters.

**Return a value:** no result.

## sharedInstance
Get singleton reference to ooVooClient SDK. Note: You need set Context before using this method else exception will throws.

**Gets a parameters list:** without parameters.

**Return a value**:

Type            | Name | Description
--------------- | ---- | --------------------------------------
**ooVooClient** | NA   | Singleton reference to ooVooClient SDK

## getAccount
Get ooVoo client account property. Use account object to perform operations such as: create account, login account, get profile ...

**Gets a parameters list:** without parameters.

**Return a value:**

Type         | Name | Description
------------ | ---- | -------------------------------------------------
**IAccount** | NA   | Returns interface to ooVoo client Account service

## getAVChat
Get ooVoo client audio video property. Use AVChat object to perform operation such as: get getVideoController, getAudioController, setListener, send....

**Parameters:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | ------------------------------------------------
**AVChat** | NA   | Returns interface to ooVoo client AVChat service

## isAuthorized
The method allows define if was performed authorizing.

**Parameters:** without parameters.

**Return a value:**

Type          | Name | Description
------------- | ---- | ------------------------------------------------
**boolean** | NA   | Returns true if was performed authorizing.

## isDeviceSupported
The method allows to define if ooVoo SDK support this device.

**Parameters:** without parameters.

**Return a value:**

Type          | Name | Description
------------- | ---- | ------------------------------------------------
**boolean**      | NA   | Returns true if supported.
## setContext
The static method allows to set application context.

**Gets a parameters list:**

Type        | Name | Description
----------- | ---- | ------------------------
**Context** | ctx  | Set application context.

 **Return a value:** no result.

## isTablet
The static method allows to detect if this a device is tablet.

**Gets a parameters list:** without parameters.

**Return a value:**

Type        | Name | Description
----------- | ---- | --------------------------------------------------
**boolean** | ---- | Returns boolean value, if this a device is tablet.

## setSslPeerVerify
The native method allows to set checking for of a secure connection.
An SSL certificate - a unique digital signature necessary for the organization of a secure connection between the client and the server.

**Gets a parameters list:**

Type        | Name | Description
----------- | ---- | ------------------------
**boolean** | state  | Define a secure connection.

 **Return a value:** no result.

## isSslPeerVerify

 The native method allows to detect if this a connection used a SSL verification.

**Gets a parameters list:** without parameters.

**Return a value:**

Type        | Name | Description
----------- | ---- | --------------------------------------------------
**boolean** | ---- | Returns Boolean value, if this a connection is a secure.

## authorizeClient
The method allows to authorize access to ooVooClient SDK. This is async method, event will raised on main thread.

**Gets a parameters list:**

Type                       | Name            | Description
-------------------------- | --------------- | ---------------------------------------------------------
**String**                 | app_token       | The application token got after registration on site.
**String**                 | version         | SDK user version.
**ooVooSdkResultListener** | result_receiver | The async listener which allows to get result on request.

**Return a value:** no result.

## setLogger
Associates a logging object with the SDK.

**Gets a parameters list:**

Type               | Name     | Description
------------------ | -------- | ---------------------------------------------------------
**LoggerListener** | listener | The async listener which allows to get result on request.
**LogLevel**       | level    | The level of log.

**Return a value:** no result.

## setLogLevel
The static method allows to set a log level in the SDK.

**Gets a parameters list:**

Type         | Name  | Description
------------ | ----- | -----------------
**LogLevel** | level | The level of log.

**Return a value:** no result.

## getSdkVersion
The method allows to get SDK version.

**Parameters:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | -----------------------
**String** | ---- | Returns version of SDK.

## updateConfig
The method allows to update user configuration and will sync local configuration for a user and backend version. Result contain only status of the operation.

**Gets a parameters list:**

Type                       | Name     | Description
-------------------------- | -------- | ---------------------------------------------------------
**ooVooSdkResultListener** | listener | The ASYNC listener which allows to get result on request.

**Return a value:** no result.

# GLPerformanceUtlis
## getCurrentCpuFrequency
The method allows to get the current frequency of CPU in Hz.

**Gets a parameters list:** without parameters.

**Return a value:**

Type        | Name | Description
----------- | ---- | ----------------------------------
**int** | ---- | Returns frequency in Hz.

## getEnableThreshold
The method allows to get the maximum time for perform action with the current resolution. If the return value from getPerfValue is bigger than the value from getEnableThreshold, GPU buffer reading for that resolution is not suggested to be used in the app.

**Gets a parameters list:** without parameters.

**Return a value:**

Type        | Name | Description
----------- | ---- | ----------------------------------
**long** | ---- | Returns suggested value about the acceptable threshold in microseconds.

## getNumCore
The method allows to get the number of the CPU core.

**Gets a parameters list:** without parameters.

**Return a value:**

Type        | Name | Description
----------- | ---- | ----------------------------------
**int** 		| ---- | Returns the number of cores.

## getPerfValue
The method allows to get the test result for specific resolution. CIF would only be tested if the VGA cannot meet the "suggested enable threshold" If the resolution was not been test function will return -1.

**Gets a parameters list:**

Type        | Name | Description
----------- | ---- | ----------------------------------
**String**  | resolution | Available resolution VGA_PERFORMANCE / CIF_PERFORMANCE

**Return a value:**

Type        | Name | Description
----------- | ---- | ----------------------------------
**long** 		| ---- | Returns average time in microsecond of GPU buffer reading.

## isTegraDetected
The method allows to get the number of the CPU core.

**Gets a parameters list:** without parameters.

**Return a value:**

Type        		| Name | Description
--------------- | ---- | ----------------------------------
**boolean** 		| ---- | Returns boolean value if this is Tegra.

# JNIObject
## isValid
The method allows to check if the object is valid.

**Gets a parameters list:** without parameters.

**Return a value:**

Type        | Name | Description
----------- | ---- | ----------------------------------
**Boolean** | ---- | Returns Boolean value if is valid.

## release
The method allows to release JNI object.

**Gets a parameters list:** without parameters.

**Return a value:** no result.

# Account
## login
The method allows you to login with an existing user.

**Gets a parameters list:**

Type                       | Name     | Description
-------------------------- | -------- | ---------------------------------------------------------
**String**                 | uid      | The ID an existing user in ooVoo.
**ooVooSdkResultListener** | listener | The async listener which allows to get result on request.

**Return a value:** no result.

## getID
The method allows to get logged in account id.

**Gets a parameters list:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | -------------------
**String** | ---- | Returns an user ID.

## logout
The method allows to perform logout an existing user.

**Gets a parameters list:** without parameters.

**Return a value:** no result.

#Device 

## getID
The method allows to get ID of device.

**Gets a parameters list:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | -------------------
**String** | ---- | Returns a device ID.

## getName
The method allows to get name of device.

**Gets a parameters list:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | -------------------
**String** | ---- | Returns a name ID.

#Effect

## getCategory
The method allows to get category of the effect.

**Gets a parameters list:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | -------------------
**String** | ---- | Returns a category of the effect.

## getIconUrl
The method allows to get URL to icon for the effect.

**Gets a parameters list:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | -------------------
**String** | ---- | Returns URL to icon for the effect.

## getID
The method allows to get unique ID of the effect.

**Gets a parameters list:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | -------------------
**String** | ---- | Returns ID of the effect.

## getName
The method allows to get name of the effect.

**Gets a parameters list:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | -------------------
**String** | ---- | Returns name of the effect.

## getPurchaseId
The method allows to get unique static ID of the effect.

**Gets a parameters list:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | -------------------
**String** | ---- | Returns static ID of the effect.

# PluginFactory

## createPluginInstance
The method allows to create a custom plugin and integrate him in ooVoo SDK.

**Gets a parameters list:** without parameters.

**Return a value:**

Type       | Name | Description
---------- | ---- | -------------------
**long** | ---- | Returns unique ID of instance.

# ooVooSdkResultListener
## onResult
The method allows to get all events from lower level of SDK.

**Gets a parameters list:**

Type               | Name   | Description
------------------ | ------ | ----------------------------------------------------------
**ooVooSdkResult** | result | The async listener which allows to get result on requests.

**Return a value: no result.**

# ooVooSdkResult
## getResult
The method allows to get a result on a request.

**Gets a parameters list:** without parameters. **Return a value:**

Type              | Name | Description
----------------- | ---- | --------------------------------
**sdk_error    ** | ---- | Returns the result on a request.

## getDescription
The method allows to get a description on a request.

**Gets a parameters list:** without parameters.

**Return a value:**

Type           | Name | Description
-------------- | ---- | -------------------------------------
**String    ** | ---- | Returns the description on a request.

## getUserInfo
The method allows to get additional information on a request.

**Gets a parameters list:** without parameters.

**Return a value:**

Type                            | Name | Description
------------------------------- | ---- | ------------------------------------------------
**`Hashtable<String, Object>`** | ---- | Returns the additional information on a request.

# LoggerListener
## LogLevel
The enum allows to get the different levels of log.

**Parameters list:**

| Values
| ------
| `int`
| 0
| 1
| 2
| 3
| 4
| 5
| 6

## fromInt
The method allows to convert a log level from integer to enum.

**Gets a parameters list:**

Type    | Name | Description
------- | ---- | --------------------------------------
**int** | e    | This is a log level in format integer.

**Return a value:**

Type         | Name | Description
------------ | ---- | --------------------
**LogLevel** | ---- | Returns a log level.

## levelToInt
The method allows to convert a log level to integer from enum.

**Gets a parameters list:**

Type         | Name  | Description
------------ | ----- | -----------------------------------
**LogLevel** | level | This is a log level in format enum.

**Return a value:**

Type    | Name | Description
------- | ---- | --------------------
**int** | ---- | Returns a log level.

## fromString
The method allows to convert a log level from string to enum.

**Gets a parameters list:**

Type       | Name | Description
---------- | ---- | -------------------------------------
**String** | s    | This is a log level in format string.

**Return a value:**

Type     | Name | Description
-------- | ---- | --------------------
LogLevel | ---- | Returns a log level.

## OnLog
The method allows to get all events from lower level of SDK. Note: must provide an implementation for this method.

**Gets a parameters list:**

Type         | Name    | Description
------------ | ------- | -----------------------------------
**LogLevel** | level   | This is a log level in format enum.
**String**   | tag     | This is ID of message.
**String**   | message | This is a body message.

**Return a value:** no result.

# AVChat
## ConferenceState
The enum allows to get the different the conference state.

**Parameters list:** Joined, Disconnected

## setListener
The method allows to set handler for receiving conference event from SDK.

**Gets a parameters list:**

Type           | Name     | Description
-------------- | -------- | ------------------------------------------------------------------------------
AVChatListener | listener | The async listener which allows to set handler for receiving conference event.

**Return a value:** no result.

## join
The method allows to perform a join conference call.

**Gets a parameters list:**

Type           | Name     | Description
-------------- | -------- | ------------------------------------------------------------------------------
AVChatListener | listener | The async listener which allows to set handler for receiving conference event.

**Return a value:** no result.

## leave
The method allows to perform a leave from conference call.

**Gets a parameters list:** without parameters.

**Return a value:** no result.

## send
The method allows to send a message to the user specification.

**Gets a parameters list:**

Type   | Name | Description
------ | ---- | -------------------------------------------------
String | uid  | Specifies the user, to which the message is sent.
byte[] | msg  | The message for sending.

**Return a value:**

Type      | Name | Description
--------- | ---- | -------------------------------
sdk_error | ---- | Returns a status about sending.

## send
The method allows to send a message to all users in conference session.

**Gets a parameters list:**

Type   | Name | Description
------ | ---- | ------------------------
byte[] | msg  | The message for sending.

**Return a value:**

Type      | Name | Description
--------- | ---- | -------------------------------
sdk_error | ---- | Returns a status about sending.

## registerPlugin
The method allows to register a custom plugin implementation for use in AVChat.

**Gets a parameters list:**

Type          | Name   | Description
------------- | ------ | --------------------------------------------------------------------
PluginFactory | plugin | The interface allow transfer custom plugin implementation to our SDK

**Return a value:** no result.

## unregisterPlugin
The method allows to un-register a custom plugin for use in AVChat.

**Gets a parameters list:**

Type          | Name   | Description
------------- | ------ | --------------------------------------------------------------------
PluginFactory | plugin | The interface allow to cancel custom plugin to our SDK

**Return a value:** no result.

## isInCallMessagesPermit
The method allows to check if you can send a message via conference.

**Gets a parameters list:** without parameters.

**Return a value:**

Type            | Name | Description
--------------- | ---- | ---------------------------------------------
boolean		| ---- | Returns boolean value, if you can send a message.

## getAvailableResolutions
The method allows to get available a resolution list in current a call.

**Gets a parameters list:** without parameters.

**Return a value:**

Type            			   | Name | Description
------------------------------------------ | ---- | ---------------------------------------------
ArrayList\<VideoController.ResolutionLevel\> | ---- | Returns a list resolutions.

## isResolutionSupported
The method allows to check, if this a resolution is supported.

**Gets a parameters list:**

Type          			| Name   | Description
------------------------------- | ------ | --------------------------------------------------------------------
VideoController.ResolutionLevel | level  | This is a resolution for checking.

**Return a value:**

Type    | Name | Description
------- | ---- | ---------------------------------------------
boolean | ---- | Returns boolean value, If there is support for the requested resolution.

## getVideoController
The method allows to get to video controller interface.

**Gets a parameters list:** without parameters.

**Return a value:**

Type		   | Name   | Description
------------------ | ------ | -----------
VideoController    |  ----  |Returns the interface of a video controller.|

## getAudioController
The method allows to get to audio controller interface.

**Gets a parameters list:** without parameters.

**Return a value:**

Type            | Name | Description
--------------- | ---- | ---------------------------------------------
AudioController | ---- | Returns the interface of an audio controller.

 

## AVChatListener
### onParticipantJoined
The method allows to receive an event listener that a participant joined to av chat session.

**Gets a parameters list:**

Type        | Name        | Description
----------- | ----------- | -----------------------------------------------------------
Participant | participant | This is participant ID.
String      | userData    | This is user's additional information but data can be null.

**Return a value**: no result.

### onParticipantLeft
The method allows to receive an event listener that a participant left the session.

**Gets a parameters list:**

Type        | Name        | Description
----------- | ----------- | -----------------------
Participant | participant | This is participant ID.

**Return a value:** no result.  

### onConferenceStateChanged
The method allows to receive an event listener about changing in session.

**Gets a parameters list:**

Type            | Name      | Description
--------------- | --------- | -----------------------------------------------------------
ConferenceState | state     | This is enum conference state.
sdk_error       | errorCode | This is an error code about changing a state of conference.

**Return a value:** no result.

### onReceiveData
The method allows to receive any data that had been sent to the user. **Gets a parameters list:**

Type       | Name   | Description
---------- | ------ | -----------------
**String** | uid    | This is user ID.
**byte[]** | buffer | This is any data.

**Return a value:** no result.

### onConferenceError
The method allows to receive an event listener about error in conference session.

**Gets a parameters list:**

Type      | Name      | Description
--------- | --------- | -----------------------------------------
sdk_error | errorCode | This is an error code about a conference.

**Return a value:** no result.  

### onNetworkReliability
The method allows to receive an information about network state.

**Gets a parameters list:**

Type | Name  | Description
---- | ----- | ------------------------
int  | score | This is a network state.

**Return a value:** no result.  

# Participant
## ParticipantType
The enum allows to get a different a types of participant.

**Parameters list:** VoIP

## getID
The method allows to get participant ID in conference.

**Gets a parameters list:** without parameters.

**Return a value:**

Type   | Name | Description
------ | ---- | ---------------------------
String | ---- | Returns the participant ID.

## getType
The method allows to get type connect of participant.

**Gets a parameters list:** without parameters.

**Return a value:**

Type            | Name | Description
--------------- | ---- | ------------------------
ParticipantType | ---- | Returns type of connect.

 

# AudioController
## AudioRouteMode
The enum allows to get the different an audio routes.

**Parameters list:** AudioRouteModeVoiceChat, AudioRouteModeVideoChat

## setListener
The method allows to set handler for receiving conference event from audio controller.

**Gets a parameters list:**

Type                    | Name     | Description
----------------------- | -------- | ------------------------------------------------------------------------------
AudioControllerListener | listener | The async listener which allows to set handler for receiving conference event.

**Return a value: no result.**

## initAudio

The method audio record/playback module. It's recommended to call this method before calling to join method.

**Gets a parameters list:**

Type                    | Name     | Description
----------------------- | -------- | ------------------------------------------------------------------------------
ooVooSdkResultListener | completion | The async listener which allows to get result on request.

**Return a value:** no result.

## uninitAudio

The method allows to perform un-init audio record/playback module.

**Gets a parameters list:**

Type                    | Name     | Description
----------------------- | -------- | ------------------------------------------------------------------------------
ooVooSdkResultListener | completion | The async listener which allows to get result on request.

**Return a value:** no result.

## isPlaybackMuted
The method allows to check if playback current state of audio stream mute or unmute.

**Gets a parameters list:** without parameters. **Return a value:**

Type    | Name | Description
------- | ---- | ---------------------------------------------------------
boolean | ---- | Returns boolean value about of the state an audio stream.

## isRecordMuted
The method allows to check if record current state mute or unmute.

Gets a parameters list: without parameters.

**Return a value:**

Type    | Name | Description
------- | ---- | --------------------------------------------------
boolean | ---- | Returns boolean value about of the state a record.

## setRecordMuted
The method allows to set record current state mute or unmute.

**Gets a parameters list:** without parameters.

Type    | Name  | Description
------- | ----- | --------------------------------------------------
boolean | state | Defines boolean value about of the state a record.

**Return a value:** no result.

## setPlaybackMuted
The method allows to set playback current state of audio stream mute or unmute.

**Gets a parameters list:** without parameters.

Type    | Name  | Description
------- | ----- | ---------------------------------------------------------
boolean | state | Defines boolean value about of the state an audio stream.

**Return a value:** no result.

## getAudioRouteController
The method allows to get audio route manager interface.

**Gets a parameters list:** without parameters.

**Return a value:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
AudioRouteController | ---- | Returns audio route manager.

##setAudioRouteMode
The method allows to set audio route mode, exists two modes *AudioRouteModeVideoChat* and *AudioRouteModeVoiceChat*.

*AudioRouteModeVoiceChat* - audio will start with audio directed to earpiece.

*AudioRouteModeVideoChat* - audio will start with audio directed to speaker.

**Gets a parameters list:**

Type	       | Name      | Description
-------------- | --------- | -----------------------------------------
AudioRouteMode | mode 	   | This is mode for audio routes.

**Return a value:** no result.
 

## AudioControllerListener
### onAudioTransmitStateChanged
The method allows to receive an event listener, that an audio transmitter has been changed.

**Gets a parameters list:**

Type      | Name  | Description
--------- | ----- | --------------------------------------------------------
boolean   | state | This is a state show if audio transmit has been changed.
sdk_error | error | This is an error code about changing.

**Return a value:** no result.

### onAudioReceiveStateChanged
The method allows to receive an event listener, that audio receiver has been changed.

**Gets a parameters list:**

Type      | Name  | Description
--------- | ----- | --------------------------------------------------------
boolean   | state | This is a state show if audio transmit has been changed.
sdk_error | error | This is an error code about changing.

**Return a value: no result.**

### onMicrophoneStateChange
The method allows to receive an event listener, that microphone status has been changed.

**Gets a parameters list:**

Type      | Name  | Description
--------- | ----- | ------------------------------------------------
boolean   | on    | This is a status of microphone has been changed.
sdk_error | error | This is an error code about changing.

**Return a value:** no result.

### onSpeakerStateChange
The method allows to receive an event listener, that speaker status has been changed.

**Gets a parameters list:**

Type      | Name  | Description
--------- | ----- | ---------------------------------------------
boolean   | on    | This is a status of speaker has been changed.
sdk_error | error | This is an error code about changing.

**Return a value:** no result.  

# AudioRoute

## getName
The method allows to get name of audio route.

**Gets a parameters list:** without parameters.

**Return a value:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
String 							 | ---- | Returns name of audio route .

## getRouteId
The method allows to get ID of audio route.

**Gets a parameters list:** without parameters.

**Return a value:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
int 							 | ---- | Returns ID of audio route .

## isActive
The method allows to check if current route is active.

**Gets a parameters list:** without parameters.

**Return a value:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
int 							 	 | ---- | Returns true if audio route is active.

# AudioRouteController

## getRoutes
The method allows to get list available of audio routes.

**Gets a parameters list:** without parameters.

**Return a value:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
ArrayList<AudioRoute> | ---- | Returns list of audio routes.

## setListener
The method allows to set handler for receiving the event from the audio route controller.

**Gets a parameters list:**

Type                    | Name     | Description
----------------------- | -------- | ------------------------------------------------------------------------------
AudioRouteControllerListener | listener | The async listener which allows to set handler for receiving the event.

**Return a value:** no result.

## setRoute
The method allows to select an audio route.

**Gets a parameters list:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
AudioRoute 					 | route | Audio route for setting.

**Return a value:**  no result.

## AudioRouteControllerListener

### onAudioRouteChanged

The method allows to receive an event listener, that an audio route has been changed.

**Gets a parameters list:**

Type      | Name  | Description
--------- | ----- | --------------------------------------------------------
AudioRoute | old_route | This is show previous position of audio route.
AudioRoute | new_route | This is show current position of audio route.

**Return a value:** no result.

# VideoController

## ResolutionLevel
The enum allows to get the different resolution.

**Parameters list:** ResolutionLevelNotSpecified, ResolutionLevelLow, ResolutionLevelMed, ResolutionLevelHigh, ResolutionLevelHD

## VideoConfigKey
The enum allows to get the key of video configuration.

**Parameters list:** kVideoCfgCaptureDeviceId, kVideoCfgResolution, kVideoCfgFps, kVideoCfgEffectId

## getConfig

The method allows to get configuration according to with a key.

**Gets a parameters list:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
VideoConfigKey 			 | key | Key of the video configuration.

**Return a value:**

Type         | Name | Description
------------ | ---- | ----------------------------
String 			 | ---- | Returns configuration key.

## setConfig

The method allows to set configuration according to with a key.

**Gets a parameters list:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
VideoConfigKey 			 | key | Key of the video configuration.

**Return a value:** no result.

## setListener
 The method allows to set handler for receiving conference event from video controller.

**Gets a parameters list:**

Type                     | Name     | Description
------------------------ | -------- | ------------------------------------------------------------------------------
IVideoControllerListener | listener | The async listener which allows to set handler for receiving conference event.

**Return a value:** no result.

## setActiveResolution
 The method allows to define the specific resolution for a camera.

**Gets a parameters list:**

Type                  | Name  | Description
--------------------- | ----- | ---------------------------------
CameraResolutionLevel | level | Defines the resolution of camera.

**Return a value:** no result.

 

## getActiveResolution
The method allows to get the resolution current the camera in uses.

**The method is depricated :**

Use instead

setConfig( VideoConfigKey.kVideoCfgResolution.ordinal(), ""+level.ordinal() );

**Gets a parameters list:** without parameters. **Return a value:**

Type                  | Name | Description
--------------------- | ---- | -----------------------------------------
CameraResolutionLevel | ---- | Returns the resolution of current camera.

## setFps
 The method allows to define the frames per second for a video.

**The method is depricated :**

Use instead

setConfig( VideoConfigKey.kVideoCfgFps, "" + fps );.

**Gets a parameters list:**

Type | Name | Description
---- | ---- | ------------------------------------------
int  | fps  | Defines the frames per second for a video.

**Return a value:** no result.

## getFps
 The method allows to get the frames per second for a video.

**The method is depricated :**

Use instead

String fps_value = getConfig( VideoConfigKey.kVideoCfgFps);

int fps    =   Integer.parseInt( fps_value.trim() );

**Gets a parameters list:** without parameters.

**Return a value:**

Type | Name | Description
---- | ---- | ------------------------------------------
int  | ---- | Returns the frames per second for a video.

 

## setActiveEffect
 The method allows to define the effect for a video.


**The method is depricated :**

Use instead

setConfig( VideoConfigKey.kVideoCfgEffectId, effect.getID() );

**Gets a parameters list:**

Type    | Name   | Description
------- | ------ | -------------------------------
IEffect | effect | Defines the effect for a video.

**Return a value:** no result.

## getActiveEffect
 The method allows to get the effect for a video.

**The method is depricated :**

Use instead

 	 String effect_id = getConfig( VideoConfigKey.kVideoCfgEffectId);

  	if( effect_id != null ) {

            ArrayList<Effect> effects = getEffectList();

            LogSdk.d( TAG, "Application -> effects " + effects );

            if( effects != null ) {

                for( Effect effect : effects )

                    {
                        if( effect.getID().equalsIgnoreCase( effect_id )) {

                            return effect;

                        }

                    }

            }

        }


**Gets a parameters list:** without parameters.




**Return a value:**

Type    | Name | Description
------- | ---- | -------------------------------
IEffect | ---- | Returns the effect for a video.

## setActiveDevice
 The method allows to define type of camera for current use, a front camera or a back camera.

**The method is depricated :**

Use instead

 setConfig( VideoConfigKey.kVideoCfgCaptureDeviceId, device.getID() );


**Gets a parameters list:**

Type                                                 | Name | Description
---------------------------------------------------- | ---- | -----------
IDevice    device    Defines type of camera for use. |      |

**Return a value:** no result.

 

## getActiveDevice
The method allows to get the type of camera used at the moment.


**The method is depricated :**

Use instead


 	String device_id = getConfig( VideoConfigKey.kVideoCfgCaptureDeviceId );

        if( device_id != null ) {

            ArrayList<VideoDevice> devices = getDeviceList();

            if( devices != null ) {

                for( VideoDevice device : devices ) {

                    if( device.getID().equalsIgnoreCase( device_id )) {

                        return device;

                    }

                }

            }

        }

**Gets a parameters list:** without parameters.

**Return a value:**

Type    | Name | Description
------- | ---- | --------------------------------------
IDevice | ---- | Returns the camera used on the moment.

## openPreview
The method allows to start get the video captures from camera. Camera must be opened before opening preview.

**Gets a parameters list:** without parameters.

**Return a value:** no result.

## closePreview
The method allows to stop get the video captures from camera.

**Gets a parameters list:** without parameters.

**Return a value:** no result.

## openCamera
The method allows to initialize the camera for use.

**Gets a parameters list:**

Type     | Name   | Description
-------- | ------ | -------------------------------------------------------------
Activity | parent | Defines the activity with which will be to interact a camera.

**Return a value:** no result.

## closeCamera
 The method allows finalize to use the camera.

**Return a value:** no result.

## startTransmit
 The method allows to start transmit video.

**Return a value:** no result.

## stopTransmit
 The method allows to stop transmit video.

**Return a value:** no result.

## isTransmited
The method allows to check if the video is transmitted at the moment.

**Gets a parameters list:** without parameters.

**Return a value:**

Type    | Name | Description
------- | ---- | -----------------------------------------------------
boolean | ---- | Returns the boolean value about transmission a video.

## bindRender
The method allows to add the specified video stream at a particular VideoView from a   particular user in conference.

**Gets a parameters list:**

Type             | Name   | Description
---------------- | ------ | -----------------------------------------------------------
**String**       | uid    | Specifies the user ID to which belongs to the video stream.
**VideoRender** | render | Defines the VideoView in which will be show video stream.

**Return a value:** no result.

## unbindRender
The method allows to remove the specific video stream at a particular VideoView from a particular user in conference.

**Gets a parameters list:**

Type             | Name   | Description
---------------- | ------ | ------------------------------------------------------------
**String**       | uid    | Specifies the user ID to which belongs to the video stream.
**VideoRender** | render | Defines the VideoView in which will be removed video stream.

**Return a value:** no result.

## registerRemote
The method allows to agree getting video stream from a particular user.

**Gets a parameters list:**

Type   | Name | Description
------ | ---- | ------------------------------------------------------------------
String | uid  | Specifies the ID of the user who agrees to receive a video stream.

**Return a value:** no result.

## unregisterRemote
The method allows to stop receive a video stream from a particular user.

**Gets a parameters list:**

Type       | Name | Description
---------- | ---- | ------------------------------------------------------------------
**String** | uid  | Specifies the user ID from which prohibits receive a video stream.

**Return a value:** no result.

## getDeviceList
The method allows to get a list all of cameras on device.

**Gets a parameters list:** without parameters.

**Return a value:**

Type             | Name | Description
---------------- | ---- | ---------------------------------------
`Array<IDevice>` | ---- | Returns array all of cameras on device.

 

## getEffectList
The method allows to get available effect list for video.

**Gets a parameters list:** without parameters.

**Return a value:**

Type             | Name | Description
---------------- | ---- | ----------------------------------------------
`Array<IEffect>` | ---- | Returns array all available effects for video.

## sizeToResolutionLevel
The method allows to get the resolution level from size of video.

**Gets a parameters list:**

Type       | Name   | Description
---------- | ----   | ------------------------------------------------------------------
int 	   | width  | This is a width of video.
int	   | height | This is a height of video.

**Return a value:**

Type             		| Name | Description
------------------------------- | ---- | ----------------------------------------------
VideoController.ResolutionLevel | ---- | Returns an enum of resolution level.


## VideoControllerListener
### RemoteVideoState
The enum allows to get a different a status from the outside incoming video.

**Parameters list:**

Item        | Description
----------- | --------------------------------
RVS_Started | Remote video started.
RVS_Stopped | Remote video stopped.
RVS_Paused  | Remote video paused by QOS/hold.
RVS_Resumed | Remote video resumed by QOS.


### onRemoteVideoStateChanged
 The method allows to receive an event listener, when remote video state has been changed.

**Gets a parameters list:**

Type             | Name   | Description
---------------- | ------ | ---------------------------------------------------
String           | uid    | This is a user id of remote video.
RemoteVideoState | state  | This is new remote video state.
int              | width  | This is a width resolution of video.
int              | height | This is a height resolution of video.
sdk_error        | error  | This is an error code about changing in conference.

**Return a value:** no result.  

### onCameraStateChanged
 The method allows to get an event listener, when camera state has been exchanged.

**Gets a parameters list:**

Type      | Name     | Description
--------- | -------- | ---------------------------------------------------
boolean   | state    | This is new camera state (ON/OFF).
String    | deviceId | This is a device ID.
int       | width    | This is a width resolution of video.
int       | height   | This is a height resolution of video.
int       | fps      | This is a Frames per Second.
sdk_error | error    | This is an error code about changing in conference.

**Return a value:** no result.

### onTransmitStateChanged
The method allows to get an event listener, when video transmit state has been exchanged.

**Gets a parameters list:**

Type      | Name  | Description
--------- | ----- | ---------------------------------------------------
boolean   | state | This is new video transmit state (ON/OFF).
sdk_error | error | This is an error code about changing in conference.

**Return a value:** no result.  

### onVideoPreviewStateChanged
The method allows to get an event listener, when preview video state has been exchanged.

**Gets a parameters list:**

Type      | Name  | Description
--------- | ----- | ---------------------------------------------------
boolean   | state | This is new preview video state (ON/OFF).
sdk_error | error | This is an error code about changing in conference.

**Return a value:** no result.

### onCameraChanged
The method allows to get an event listener, when active device has been exchanged.

**Gets a parameters list:**

Type      | Name      | Description
--------- | --------- | ---------------------------------------------------
String    | deviceId  | This is camera device ID.
sdk_error | errorCode | This is an error code about changing in conference.

**Return a value:** no result.

# VideoDevice

## getAvailableResolutions
The method allows to get a list available the resolutions of video.

**Gets a parameters list:** without parameters.

**Return a value:**

Type            			   | Name | Description
------------------------------------------ | ---- | ---------------------------------------------
ArrayList\<VideoController.ResolutionLevel\> | ---- | Returns a list resolutions.

## isResolutionSupported
The method allows to check, if this a resolution level is supported.

**Gets a parameters list:**

Type          			| Name   | Description
------------------------------- | ------ | --------------------------------------------------------------------
VideoController.ResolutionLevel | level  | This is a resolution for checking.

**Return a value:**

Type    | Name | Description
------- | ---- | ---------------------------------------------
boolean | ---- | Returns boolean value, If there is support for the requested resolution.

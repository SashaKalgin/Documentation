# Developing with the WebRTC SDK
<!-- TOC depth:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Developing with the WebRTC SDK](#developing-with-the-webrtc-sdk)
	- [Introduction](#introduction)
	- [Core Concepts](#core-concepts)
		- [What is WebRTC?](#what-is-webrtc)
		- [What is an Application ID?](#what-is-an-application-id)
		- [What is an Application Token?](#what-is-an-application-token)
		- [What is a Development Application Token?](#what-is-a-development-application-token)
		- [What is an ooVoo Video Conference?](#what-is-an-oovoo-video-conference)
		- [What is a Conference ID?](#what-is-a-conference-id)
		- [What is a Participant?](#what-is-a-participant)
		- [What is a Participant ID?](#what-is-a-participant-id)
	- [Getting Started With the WebRTC SDK Package](#getting-started-with-the-webrtc-sdk-package)
		- [What browsers are supported by the ooVoo WebRTC SDK?](#what-browsers-are-supported-by-the-oovoo-webrtc-sdk)
		- [How do I setup the ooVoo WebRTC SDK in my development environment?](#how-do-i-setup-the-oovoo-webrtc-sdk-in-my-development-environment)
		- [How do I deploy and run the ooVoo WebRTC sample app included in the SDK download package?](#how-do-i-deploy-and-run-the-oovoo-webrtc-sample-app-included-in-the-sdk-download-package)
	- [Developing With the WebRTC SDK](#developing-with-the-webrtc-sdk)
		- [How can I get Application ID and Application Token?](#how-can-i-get-application-id-and-application-token)
		- [How do I connect my users in a video call?](#how-do-i-connect-my-users-in-a-video-call)
		- [How do I Initialize the SDK/Client Side Login?](#how-do-i-initialize-the-sdkclient-side-login)
		- [Client Side Login:](#client-side-login)
		- [Initialization](#initialization)
		- [Conference Creation](#conference-creation)
		- [How do I configure my local media stream?](#how-do-i-configure-my-local-media-stream)
		- [How do I join a conference?](#how-do-i-join-a-conference)
		- [How do I control my local audio stream in a conference?](#how-do-i-control-my-local-audio-stream-in-a-conference)
		- [How do I control remote participants audio stream in a conference?](#how-do-i-control-remote-participants-audio-stream-in-a-conference)
		- [How do I control my local video stream in a conference?](#how-do-i-control-my-local-video-stream-in-a-conference)
		- [How do I control remote participants video stream in a conference?](#how-do-i-control-remote-participants-video-stream-in-a-conference)
		- [How can I send messages while in a conference?](#how-can-i-send-messages-while-in-a-conference)
	- [Events](#events)
		- [onConferenceStateChanged ( evt )](#onconferencestatechanged-evt-)
		- [onParticipantJoined ( evt )](#onparticipantjoined-evt-)
		- [onParticipantLeft ( evt )](#onparticipantleft-evt-)
		- [onRemoteVideoStateChanged ( evt )](#onremotevideostatechanged-evt-)
		- [onVideoRotate( evt )](#onvideorotate-evt-)
		- [onRecvData ( evt )](#onrecvdata-evt-)
	- [Error Codes](#error-codes)
	- [Server-to-Server Login](#server-to-server-login)

<!-- /TOC -->

## Introduction
Thank you for your interest in the ooVoo Video Chat SDK. The ooVoo SDK encapsulates the technical complexity of implementing and delivering a high quality, one-to-one and group video communications service over the Internet under a set of easy to use APIs exposed via the SDK, making it easy for you to quickly integrate video experiences into your own apps.

The video service offered via the SDK is powered by ooVoo's proven and scalable global cloud infrastructure and already provides over 1 billion video minutes to millions of users per month.

Below you will find complete documentation for the WebRTC JS SDK that will have you up and running in no time. Documentation will be added for additional platforms as well, as soon as they are released.

Happy Hacking!

## Core Concepts
### What is WebRTC?
WebRTC is a standard for enabling Real Time Communications including audio, video and data transmission between two web browsers without the need for additional plugins.

### What is an Application ID?
An Application ID is an ID issued by ooVoo to a developer that is used to uniquely identify the developer. You should keep your Application ID secure.

### What is an Application Token?
An Application Token is a shared secret between ooVoo and a developer that is used for authenticating and authorizing an Application ID identifying the specific developer. You should keep your Application Tokens secure.  

There are several types of tokens you will need to familiarize yourself with. First, there are the two token types which let you authenticate to the service, Web and Native. Web token types are for servers and clients which are web based. Native token types are for mobile devices running iOS and Android.

There also Session tokens which authenticate you for a given period of time after you have authenticated properly. Based on which form of authentication you are using (client or server-to-server) you will initiate a login with get the session token as a callback. For client logins, you will first login with your web token, and then call Init which the returned sessions token.

For server-to-server logins, you will do the reverse, call Init with the web token and then login using the session token.

### What is a Development Application Token?
A Development Application Token is an application token assigned by ooVoo to a developer for the purpose of development. It allows the developer access to a limited scope development backend. Once the developer's application is ready for deployment, the development application Token must be replaced with a production Application Token to allow the application to access the full ooVoo production infrastructure.

### What is an ooVoo Video Conference?
An ooVoo Video Conference is where ooVoo video communication takes place. It is a logical entity representing the collection of resources allocated in ooVoo cloud and the client connections participating in the video call.  

Via the ooVoo SDK, each end user's application is able to open a connection to a given video conference hosted in the ooVoo cloud. Through that connection the end user application may choose to receive and stop receiving one, some, or all of the audio-video streams available in the conference. The end user application may also choose to send and stop sending its own audio-video stream to the conference over the same connection.

The ooVoo SDK also allows an end user application to query the video conference for information, and get status updates when the conference environment changes, for example, when a user joins or leaves the conference.

### What is a Conference ID?
A Conference ID is a unique identifier assigned by the developer to each ooVoo video conference it creates. In addition, ooVoo service internally creates a globally unique identifier to be associated with each Conference ID a developer registers with ooVoo.

### What is a Participant?
A Participant in an ooVoo Video Conference is a user who has successfully connected to the conference session. A participant may receive any or all audio video streams in the conference, as well as sending its own audio and video streams into the conference. The ooVoo SDK provides the developer full control of which audio video streams to send/receive by a participant.

### What is a Participant ID?
A Participant ID is a unique identifier assigned by the ooVoo video service for each participant in an ooVoo video conference, upon a user's successful connection to the conference session.

## Getting Started With the WebRTC SDK Package
### What browsers are supported by the ooVoo WebRTC SDK?
Currently the WebRTC Standard is supported by the following browsers:
- Chrome 35 and derivatives (Canary, Chromium, etc.)
- Firefox 30
- Opera 22
- Safari and Internet Explorer are not supported yet. We recommend upgrading your browser to the latest version to properly support our WebRTC SDK.

### How do I setup the ooVoo WebRTC SDK in my development environment?
In order to get up and running just open the demo.html file in any text editor or development environment. It is a barebones starting point which you can build around and in it you will find the necessary javascript libraries already included. If you'd like not to use the demo.html file then make sure you include the following lines in your own app:

```javascript
<script src="https://code.oovoo.com/webrtc/oovoosdk-2.0.0.min.js"></script>
```

and make sure to define the necessary variables as is referenced in the demo.html file.

### How do I deploy and run the ooVoo WebRTC sample app included in the SDK download package?
To run the WebRTC sample app, just place the files in a directory that is accessible from the document root of your web server. Make sure you edit the demo.html file or your own code to include your AppID , APP Token & conference ID (roomID), the following parameters are optional, (get default value): frame per second, resolution level and your name. Please follow the example below:

````html
<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <title></title>
```javascript
<script src="https://code.oovoo.com/webrtc/oovoosdk-2.0.0.min.js"></script>
    <script type="text/javascript">
        var conference = null;
        var conferenceId = "OOVOO_WEB_RTC";
        var appToken = "PUT APPLICATION TOKEN HERE";
        var sessionToken = getQSParam("t");
        var participantId = getQSParam("pid");

        if (!sessionToken) {
            //login to get session token
            participantId = "participant uniqe id";
            //for example (get random id)
            participantId = Math.floor(Math.random() * 9999999999) + 1000000000;

            var redirectUrl = "url to send response with the session token"
            redirectUrl = location.href + "?pid=" + participantId;
            ooVoo.API.connect({
                token: appToken,
                isSandbox: false,
                userId: participantId,
                callbackUrl: redirectUrl
            });
        }
        else {
            ooVoo.API.init({
                userToken: sessionToken
            }, onAPI_init);
        }

        function onAPI_init(res) {
            conference = ooVoo.API.Conference.init({ video: true, audio: true }, onConference_init);
        }
        function onConference_init(res) {
            if (!res.error) {
                //register to conference events
                conference.onParticipantJoined = onParticipantJoined;
                conference.onParticipantLeft = onParticipantLeft;
                conference.onLocalStreamPublished = onStreamPublished;
                conference.onConferenceStateChanged = onConferenceStateChanged;
                conference.onRemoteVideoStateChanged = onRemoteVideoStateChanged

                conference.setConfig({
                    videoResolution: ooVoo.API.VideoResolution["HIGH"],
                    videoFrameRate: new Array(5, 15)
                }, function (res) {
                    if (!res.error) {
                        conference.join(conferenceId, participantId, sessionToken, "participant name", function (result) { });
                    }
                });
            }
        }

        function onStreamPublished(stream) {
            document.getElementById("localVideo").src = URL.createObjectURL(stream.stream);
        }

        function onParticipantLeft(evt) {
            if (evt.uid) {
                document.getElementById("vid_" + evt.uid).remove();
            }
        }
        function onParticipantJoined(evt) {
            if (evt.stream && evt.uid != null) {
                var videoElement = document.createElement("video");
                videoElement.id = "vid_" + evt.uid;
                videoElement.src = URL.createObjectURL(evt.stream);
                videoElement.setAttribute("autoplay", true);
                document.body.appendChild(videoElement);
            }
        }
        function onConferenceStateChanged(evt) {
        }
        function onRemoteVideoStateChanged(evt) {
        }

        function getQSParam(name) {
            name = name.replace(/[\[]/, "\\[").replace(/[\]]/, "\\]");
            var regex = new RegExp("[\\?&]" + name + "=([^&#]*)"),
                results = regex.exec(location.search);
            return results === null ? "" : results[1].replace(/\+/g, " ");
        }
    </script>
</head>
<body>
    <video id="localVideo" style="width:50%; height:auto;" autoplay muted></video>
</body>
</html>
````

Then browse to the page using either Chrome, Firefox Or Opera. [http://{your-website}/demo.html](http://{your-website}/demo.html)

## Developing With the WebRTC SDK
Check out our developer portal and dashboard at [http://developer.oovoo.com](http://developer.oovoo.com). There you can generate AppIDs, tokens and track usage statistics.

### How can I get Application ID and Application Token?
Application ID and Application Token are unique identifiers assigned by ooVoo for each developer. They are required for accessing the ooVoo video cloud service via the ooVoo SDK. After you have successfully signed up to become an ooVoo SDK developer, you should receive email from us to verify your address. Once verification is complete, you will be able to log into the developer dashboard at [http://developer.oovoo.com](http://developer.oovoo.com) and generate AppIDs and Tokens.

Application ID and Application Token are the only way ooVoo uses to identify you as a unique and legitimate ooVoo SDK developer. You must exercise caution to keep them secure. If you ever forget/lose your ID and/or Token, please contact ooVoo by emailing to [sdk.support@oovoo.com](mailto:sdk.support@oovoo.com) or contact your designated ooVoo developer advocate immediately.

You will need two types of tokens for WebRTC applications. You will define a domain for your Application ID in the dashboard and then create two tokens. One token type is a Web token, this is used for web clients. The other token type is Native. This token type is for mobile devices which will be connecting to the same session.

>Please note that Web token types will not work on iOS and Android mobile devices. You must create a Native token for those devices.

### How do I connect my users in a video call?
In ooVoo a video call is technically named as "conference". Each conference is identified by a unique "Conference ID". To connect two or more users of your application in a video call, you simply put those users in the same ooVoo conference by having them joining conference using the same Conference ID.  It should be noted that ooVoo SDK does not handle the "signaling" steps per se between the end users of your application. It is up to you the developer to manage the distribution of the corresponding Conference ID to the target end user(s) by your own application logic.

### How do I Initialize the SDK/Client Side Login?
> Please note the changes to the initialization flow since the first release.

When trying to create or join a conference, you must first login in from either the server or client side to authenticate.

Afterwards, the starting point for your app will be to call the initialization function `ooVoo.API.init` as described below. This method is used to initialize and setup the SDK. You won't need to re-use this method, but you may want to customize the parameters used. All other SDK related function calls must be called after this one, since they won't exist until you do.

### Client Side Login:
`ooVoo.API.connect (params)``

Parameters:

Name        | Type    | Description                                                                                                                                                                                             | Default
----------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------
params      | object  | A collection of initialization parameters that control the setup of the SDK.                                                                                                                            | required
token       | string  | Your application Token, (type WEB). If you don't have one find it in the App dashboard or go there to create a new app.                                                                                 | required
isSandbox   | boolean | <ul><li>1. Login using App Token(WEB) to retrieve user session token</li><li> 2.    Init from client side – using user session token</li></ul>                                                          | true
userId      | string  | application unique participant id                                                                                                                                                                       | required
callbackUrl | string  | The URL you will be redirect post login success. (this url contains your session token) **the redirect URL you provide should be under the permitted domains you allowed on ooVoo sdk developer site**. | required

Example:

```javascript
  ooVoo.API.connect({
                token: “your app token”,
                isSandbox:true,
                userId: “unique user ID”,
                callbackUrl: “redirectUrl”
            });
```

For examples of Server-to-Server login please click here:

[Server-to-Server Login](##Server-to-Server Login)

### Initialization
Function:

```javascript
ooVoo.API.init(params,onInitComplete)
```

Parameters:

Name           | Type         | Description                                                                                                                                                                                                                | Default
-------------- | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------
params         | object       | A collection of initialization parameters that control the setup of the SDK.                                                                                                                                               | required
userapp_token  | string       | Login using App Token(WEB) to retrieve user session token.<br/>Init from client side – using user session tokenYour application Token. If you don't have one find it in the App dashboard or go there to create a new app. | required
onInitComplete | InitDelegate | A function that will be called once all data structures in the SDK are initialized; any code that should synchronize with the ooVoo/Conference session should be in onInitComplete().                                      | none, required

Example:

```javascript
ooVoo.API.init {
     userToken   : '{your-user-session-token}',
  }}, function(res) {
  if(!res.error) {
     console.log("Api initialize succeeded, now you can initialize new conference");
 }});
```

### Conference Creation
Once you have initialized the SDK you are ready to create a conference object. The Conference Object provides connection, local stream publication and remote video stream registration  which will be used to manage the conference along with the local/remote AV streams and browser event handling.

`ooVoo.API.Conference.init` creates a new conference object.

```javascript
var conferenceObj = ooVoo.API.Conference.init(params,onInitComplete)
```

Parameters:

Name           | Type         | Description                                                                                                                                               | Default
-------------- | ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------
params         | object       | A collection of initialization parameters that control the setup of the Conference.                                                                       | Can be null
-audio         | boolean      | Enable local audio stream on the conference For audio only session set false in addition to :params = null in setConfig                                   | true
-video         | boolean      | Enable local video stream on the conference                                                                                                               | true
onInitComplete | InitDelegate | A function that will be called once ooVoo.API is initialized; any code that should synchronize with the Conference session should be in onInitComplete(). | none, required

Example:

```javascript
var conferenceObj = null;
conferenceObj = ooVoo.API.Conference.init({ video: true, audio: true }, onConference_init);
function onConference_init (res) {
if(!res.error) {
console.log("Conference initialize succeeded, now it’s a good time to register the conference events");
   conferenceObj.onParticipantJoined = onParticipantJoined;
   conferenceObj.onParticipantLeft = onParticipantLeft;
   conferenceObj.onRecvData = onRecieveData;
   conferenceObj.onConferenceStateChanged = onConferenceStateChanged
 }
}
```

### How do I configure my local media stream?
Once you have instantiated a Conference Object you can now use `Conference.setConfig()` to configure your local stream.

```javascript
conferenceObj.setConfig(params,onConfigComplete);
```

Parameters:

Name             | Type           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                            | Default
---------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------
params           | object         | A collection of initialization parameters that control the setup of the Conference.                                                                                                                                                                                                                                                                                                                                                                    | null
videoResolution  | enum           | Sets the video resolution of the conference, any resolution up to the following resolutions are supported depending on device.<br/>Enum values:<ul><li>ooVoo.API.VideoResolution.NORMAL(352\*288)</li><li>ooVoo.API.VideoResolution.HIGH(640\*480)</li><li>ooVoo.API.VideoResolution.HD(1280\*720)</li></ul>For audio only session, set `Null` in addition to: `videoFrameRate` & `audio:false` in: `ooVoo.API.Conference.init(params,onInitComplete)` | required
videoFrameRate   | Int[]          | Sets the minimum an maximum video frame rate of the conference. Value can be number between 5 and 30. For audio only session, set `Null` in addition to: `videoResolution` & `audio:false` in `ooVoo.API.Conference.init(params,onInitComplete)`                                                                                                                                                                                                       | 15
onConfigComplete | ConfigDelegate | A function that will be called once ooVoo.API is initialized; any code that should synchronize with the Conference session should be in onConfigComplete().                                                                                                                                                                                                                                                                                            | none, required

Example:

```javascript
conferenceObj.setConfig({
    videoResolution: ooVoo.API.VideoResolution.HIGH,
    videoFrameRate: 15
}, function(res) {
  if(!res.error) {
     console.log("Video Configuration succeeded, now all set to join a conference session");
 }
});
```

### How do I join a conference?
You can join a conference by calling `Conference.join()` as shown below. Calling this function will also trigger some events. We will discuss events more in detail later in this document.

```javascript
conferenceObj.join(confid,uid,user_data);
```

Parameters:

Name      | Type   | Description                                                                               | Default
--------- | ------ | ----------------------------------------------------------------------------------------- | --------
confid    | string | Application unique conference id                                                          | required
uid       | string | Application unique participant id                                                         | required
user_data | string | Application data - for application usage. This data returned in onParticipantJoined event | Null

Triggered Events:
- onConferenceStateChanged
- onParticipantJoined

Example:

```javascript
conferenceObj.join('{unique-session-id}', '{unique-user-id}',
{data-to-pass}, function (res) {
  if(res.error) {
     console.log("Error occurred");
 }
});
```

### How do I control my local audio stream in a conference?
You can control the muting/unmuting of you audio in a conference and also check the status of your own audio in a conference using the following functions:

Muting/Unmuting:

`conferenceObj.setLocalAudioMute(bool);`

Parameters:

Name | Type    | Description                   | Default
---- | ------- | ----------------------------- | --------
Val  | boolean | true - muted, false - unmuted | required

Checking Status:

`conferenceObj.getLocalAudioMute();`

Returns:

Boolean, true - muted, false - unmuted

### How do I control remote participants audio stream in a conference?
You can control the muting/unmuting of a remote participants audio in a conference and also check the status of their audio in a conference using the following functions:

Muting/Unmuting:

`conferenceObj.setRemoteAudioMute(bool);`

 Parameters:

Name | Type                                  | Description | Default
---- | ------------------------------------- | ----------- | -------
val  | boolean true - muted, false - unmuted | required    |

Checking Status:

`conferenceObj.getRemoteAudioMute();`

Returns:

Boolean, true - muted, false – unmuted

### How do I control my local video stream in a conference?
You can control the publishing/unpublishing of your video in a conference and also check the status of your own video in a conference using the following functions:

Publish video:  `conferenceObj.playLocalVideo();`

Triggered Events:
- onRemoteVideoStateChanged

Stop publishing:

`conferenceObj.stopLocalVideo();`

Triggered Events:
- onRemoteVideoStateChanged

Check Status:

`conferenceObj.getLocalVideoState();`

Returns Boolean, true - stopped, false - play

### How do I control remote participants video stream in a conference?
You can control the publishing/unpublishing of participants video in a conference using the following functions:

Start Video:

`conferenceObj.registerRemoteVideo(uid);`

Parameters:

Name | Type   | Description                       | Default
---- | ------ | --------------------------------- | --------
uid  | string | Application unique participant id | required

 Triggered Events:
- onRemoteVideoStateChanged

Stop Video:

`conferenceObj.unRegisterRemoteVideo(uid);`

Parameters:

Name | Type   | Description                       | Default
---- | ------ | --------------------------------- | --------
uid  | string | Application unique participant id | required

Triggered Events:
- onRemoteVideoStateChanged

### How can I send messages while in a conference?
You can send messages while in a conference by calling the `Conference.sendData()` function.

`conferenceObj.sendData(uid,to_uid,data);`

Parameters: |Name|Type|Description|Default| |-|-|-|-| |uid|String|Application unique sender id|required| |to_uid|String|Application unique participant id or  "" (empty string) value to send for all participants|required| |data|String|Data to Send|required

Triggered Events:
- onRecvData

How do I leave a conference? You can disconnect from a conference by calling `Conference.disconnect()`:

`conferenceObj.disconnect();`

Triggered Events:
- onConferenceStateChanged
- onParticipantLeft

## Events
The events your app may receive during a conference consist of the following categories:
- Conference status change: e.g., participant joins, leave the conference.
- Participant status change: e.g., participant's audio video stream turned on/off.
- Connection status change: e.g., reporting connection quality issues.
- Application status: e.g., ooVoo SDK errors.

Below is a list of that may be triggered by API calls:

### onConferenceStateChanged ( evt )
Indicates conference states:

Parameters:

Name          | Type   | Description
------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
evt           | object | Contains information about the event
evt.state     | Enum   | <ul><li>ooVoo.API.ConferenceStateEventType.ACCESS_ACCEPTED<br/>(Indicates user has agreed to open his camera and microphone)</li><li>ooVoo.API.ConferenceStateEventType.JOINED<br/>(Joined to conference)</li><li>ooVoo.API.ConferenceStateEventType.ACCESS_DENIED<br/>(Indicates user has denied to open his camera and microphone.)</li><li>ooVoo.API.ConferenceStateEventType.CONNECTED<br/>(Connected to conference server.)</li><li>ooVoo.API.ConferenceStateEventType.DISCONNECTED<br/>(Disconnected form conference on connection)</li><li>ooVoo.API.ConferenceStateEventType.RECONNECTING<br/>(Reconnecting to conference server.)</li><li>ooVoo.API.ConferenceStateEventType.RECONNECTED<br/>(Reconnected to conference server.)</li><li>ooVoo.API.ConferenceStateEventType.DEVICE_NOT_FOUND<br/>(Indicates that a selected cam/mic device has not been found)</li><li>ooVoo.API.ConferenceStateEventType.CAM_RES_NOT_SUPPORTED<br/>(Selected camera resolution is not supported by the hardware)</li></ul>
evt.errorCode | string | Disconnect reason

### onParticipantJoined ( evt )
Indicates that participant has joined to the conference Parameters:

Name          | Type   | Description
------------- | ------ | ------------------------------------
evt           | object | Contains information about the event
evt.uid       | string | Application unique participant id
evt.stream    | stream | Video stream object
evt.user_data | string | Application data

### onParticipantLeft ( evt )
Indicates that participant has left from the conference

Parameters:

Name    | Type   | Description
------- | ------ | ------------------------------------
evt     | object | Contains information about the event
evt.uid | string | Application unique participant id

### onRemoteVideoStateChanged ( evt )
Indicates the remote video stream states

Parameters:

Name       | Type   | Description
---------- | ------ | --------------------------------------------------------------------------------------
evt        | object | Contains information about the event
evt.uid    | string | Application unique participant id
evt.state  | string | One of the following values:<br/><ul><li>PLAY</li><li>PAUSED</li><li>STOPPED</li></ul>
evt.stream | stream | Video stream object

### onVideoRotate( evt )
Indicates video Rotation and/or Mirror

Parameters:

Name    | Type   | Description
------- | ------ | ------------------------------------
evt     | object | Contains information about the event
evt.uid | string | Application unique participant id
evt.deg | int    | The Rotation Angle
evt.mrr | bool   | Is Mirrored

### onRecvData ( evt )
Indicates the incoming data, sent by remote participant  

Parameters:

Name     | Type   | Description
-------- | ------ | ------------------------------------
evt      | object | Contains information about the event
evt.uid  | string | From participant id
evt.data | string | Sent application data

## Error Codes
The following is a list of error messages you may encounter:

Code              | Group                      | Name                                          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Comment
----------------- | -------------------------- | --------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -----------------------------
0                 | Success                    | Success                                       | The request has succeeded.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
-20000            | Internal Application Error | UnspecifiedError                              | The application encountered an unexpected condition                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
-30xxx            | **Authentication Failed**  |                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
-30000            | Authentication             | AuthenticationFailed                          | Login                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
-30001            | Authentication             | InvalidToken                                  | Session Token not provided or invalid<br/><ul><li>Token was not provided</li><li>Token is invalid (or expired, blocked etc) and a new one needs to be requested.                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Renew Token or Login required
~~-30002~~        | ~~Authentication~~         | ~~Expired token~~                             | ~~Token has expired and a new one needs to be requested~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Deprecated. Use -30001
-30003            | Authentication             | InvalidAvsKey                                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
-30004            | Authentication             | BlockedAppId                                  | ApplicationId is blocked                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
-30005            | Authentication             | InvalidEnvironment                            | Application reached wrong URL environment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
-35xxx            | **Authorization Failed**   |                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
-35001            | Authorization Failed       | NotAuthorized                                 | Authentication succeeded, but Application does not have permission for this action.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
~~-36001~~        | ~~Authorization Failed~~   | ~~ThrottledDown~~                             | ~~User is on blacklist by AppId or ip~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | mistake
-40xxx<br/>-50xxx | Bad Request                |                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
-40000            | Bad Request                | BadRequest                                    | <ul><li>The request could not be understood by the application due to malformed syntax or required parameter was missing.</li><li>This is also used if the resource ID in the path is incorrect or parameter in QueryString is incorrect or missing.</li><li>The application is refusing to process the request because the content type of the media is in a format not supported by the requested resource for the requested method.</li><li>Media not supplied in the request or empty.</li><li>The application is refusing to process a request because the request media is larger than allowed for given content type.</li></ul> |
~~-40001~~        | ~~Bad Request~~            | ~~No content found~~                          | ~~No content found in a body of the request (POST method only).~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Deprecated.<br/>Use -40000
~~-40002~~        | ~~Bad Request~~            | ~~Missing required parameter in payload.~~    | ~~No parameter found in a body of the request (POST method only).~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Deprecated.<br/>Use -40000
~~-40003~~        | ~~Bad Request~~            | ~~Missing required parameter in QueryString~~ | ~~No parameter found in a QueryString of the request.~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Deprecated.<br/>Use -40000
~~-40004~~        | ~~Bad Request~~            | ~~Invalid value in payload~~                  | ~~One of the arguments provided to method is not valid~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Deprecated.<br/>Use -40000
~~-40005~~        | ~~Bad Request~~            | ~~Invalid value in QueryString~~              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Deprecated.<br/>Use -40000
-50000            | Not Found                  | InvalidApiVersion                             | Requested API version not supported                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
-50001            | Not Found                  | InvalidResource                               | The resource not was found.<br/>Example: given ooVooId doesn't exist.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
-50002            | Not Found                  | InvalidEndpoint                               | Example: trying to access the wrong URI.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
~~-60000~~        | ~~Operation Failed~~       | ~~Requested Entity too large~~                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Deprecated.<br/>Use -40000
-60001            | Operation Failed           | InvalidOperation                              | Invalid operation                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
-601XX            | Operation Failed           | Invalid content type of media                 | Error code pattern for media issues.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
~~-60100~~        | ~~Operation Failed~~       | ~~Invalid content type of media~~             | ~~The content type of the media could not be recognized by the application.~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Deprecated.<br/>Use -40000
~~-60101~~        | ~~Operation Failed~~       | ~~Unsupported Content type of media~~         | ~~The application is refusing to process the request because the content type of the media is in a format not supported by the requested resource for the requested method.~~                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Deprecated.<br/>Use -40000
~~-60102~~        | ~~Operation Failed~~       | ~~Media too large~~                           | ~~The application is refusing to process a request because the request media is larger than allowed for given content type.~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Deprecated.<br/>Use -40000
~~-60103~~        | ~~Operation Failed~~       | ~~No media supplied~~                         | ~~Media not supplied in the request or empty.~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Deprecated.<br/>Use -40000
-602XX            | Operation Failed           | Invalid content type of PostFrame             | Error code pattern for PostFrame issues.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
~~-60200~~        | ~~Operation Failed~~       | ~~Invalid content type of PostFrame~~         | ~~The content type of the PostFrame could not be recognized by the application.<br/> (Methods with post_frame only).<br/>Will be used in future versions, not in use now.~~                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Deprecated.<br/>Use -40000
~~-60201~~        | ~~Operation Failed~~       | ~~Unsupported content type of PostFrame~~     | ~~The application is refusing to process the request because the content type of the PostFrame is in a format not supported by the requested resource for the requested method.<br/>(Methods with post_frame only).~~                                                                                                                                                                                                                                                                                                                                                                                                                  | Deprecated.<br/>Use -40000
~~-60202~~        | ~~Operation Failed~~       | ~~PostFrame too large~~                       | ~~The application is refusing to process a request because the request PostFrame is larger than allowed for given content type.<br/>(Methods with post_frame only).~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Deprecated.<br/>Use -40000
~~-60203~~        | ~~Operation Failed~~       | ~~No PostFrame supplied~~                     | ~~PostFrame not supplied in the request or empty.<br/>(Methods with post_frame only).~~                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Deprecated.<br/>Use -40000
-603XX            | Operation Failed           | Invalid Business case                         | Invalid business cases                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
-60301            | Operation Failed           | GroupsLimitExceeded                           | The given user has created limit number of groups                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
-60302            | Operation Failed           | UserIdNotAvailable                            | User trying to perform registration with ooVooId already exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
-60303            | Operation Failed           | EmailNotAvailable                             | User trying to perform registration with email already exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
-60401            | Operation Failed           | InvalidVerificationCode                       | The code provided by client does not match the code sent by backend                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
-60501            | Operation Failed           | BlockedAreaCode                               | The phone dialed by client is blocked                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
-60502            | Operation Failed           | NoCredits                                     | User is out of credits/phone minutes.<br/>User can't make a phone call.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
-60503            | Operation Failed           | UnsupportedPhone                              | User supplied unsupported phone number                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
-60504            | Operation Failed           | PhoneAlreadyVerified                          | User trying to verify same phone number as already verified for his ooVoo id.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
-606XX            | Operation Failed           | Invalid Billing operation                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
-60601            | Operation Failed           | InvalidReceipt                                | User provides invalid receipt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |

## Server-to-Server Login
> Note: You must configure your domain on [https://developer.oovoo.com](https://developer.oovoo.com) developer portal in order be able to use Server-to-Server login.  Use 127.0.0.1 if you are testing to a locally deployed demo

Parameters:

Name    | Type                 | Description                                                                                                                                                                                                                                                                                                                     | Default
------- | -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------
origin  | string               | The domain developer has been configured on ooVoo SDK  developer site for his app ID                                                                                                                                                                                                                                            | empty
postUrl | string               | ooVoo backend URL<br/>sandbox:<br/>  [https://connect.oovoo.com/1.0/sso/app/login/s2s](https://connect.oovoo.com/1.0/sso/app/login/s2s)<br/>production:<br/> [https://connect.oovoo.com/1.0/sso/app/login/s2s](https://connect.oovoo.com/1.0/sso/app/login/s2s)<br/>:params:<br/>-at:={Your App token}&ct=1&cst=2&sv=1.8&cv=0.2 | required
content | string : format json | "{ \"payload\": { \"user_id\":'YourUserID-unique'} }"<br/>Params: user_id Application unique participant id                                                                                                                                                                                                                     | required

ASP.Net Sample Code

```asp
private string GetUserToken()
        {
        using(WebClient client = new WebClient())
        {  
          string origin = "YOUR APP DOMAIN"
          string postUrl ="https://connect.dev.oovoo.com/1.0/sso/app/login?at={Your) App Token, (WEB type)} &ct=1&cst=2&sv=1.8&cv=0.2";

           string content = "{ \"payload\": { \"user_id\":'foofoo'} }";
           //request
           WebRequest request = WebRequest.Create(postUrl);
           byte[] byteArray = Encoding.UTF8.GetBytes(content);
           request.Method = "POST";
           request.ContentType = "application/json";
           request.ContentLength = byteArray.Length;
           request.Headers.Add("Origin", origin);

           Stream dataStream = request.GetRequestStream();
           dataStream.Write(byteArray, 0, byteArray.Length);
           dataStream.Close();
           //response
           WebResponse response = request.GetResponse();
           dataStream = response.GetResponseStream();
           StreamReader reader = new StreamReader(dataStream);
           string responseFromServer = reader.ReadToEnd();
           dynamic res = Newtonsoft.Json.JsonConvert.DeserializeObject(responseFromServer);
           reader.Close();
           dataStream.Close();
           response.Close();
           if (res != null && res.payload != null && res.payload.token != null)
           {
               return res.payload.token.ToString();
           }
           throw new ArgumentException("get user token failed");
       }
    }
```

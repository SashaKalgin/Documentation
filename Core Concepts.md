# Core Concepts

## What is an Application ID?

An Application ID is unique ID you generate in the Developer Dashboard to identify your application. You can have multiple applications/application IDs under your account (i.e., if you develop more than one app). You should keep your Application IDs secure.

## What is an Application Token?

An Application Token is a shared secret between ooVoo and a developer that is used for authenticating and authorizing the specific application. An app can have multiple tokens based on usage/developments needs. You should keep your Application Tokens secure.

## What are the Different Types of Application Tokens?

#### Native Token
A "Native" token is for applications which will run natively on the target device.

#### Web Token
A "Web" token is for applications which will run on the web (using WebRTC) and authenticate either client-to-server or server-to-server.

#### Domain
Applications with "Web" tokens require you to specify a domain in order to ensure that communications is secure. You can specify an actual domain on which your application is hosted or use 127.0.0.1 for locally hosted apps.

## What is a Development Token vs a Production Token?

A development token is an application token assigned by ooVoo to you for the purpose of development. It allows you to access to a limited scope development backend. Once your application is ready for deployment, the development token must be replaced with a production token to allow the application to access the full ooVoo production infrastructure.

## What is an ooVoo Video Conference?

An ooVoo Video Conference is where ooVoo video communication takes place. It is represents the collection of resources allocated in ooVoo cloud and the client connections participating in the video call.

Via the ooVoo SDK, each application is able to open a connection to a given video conference hosted on the ooVoo Video Platform. Through that connection the application may choose to receive and stop receiving one, some, or all of the audio-video streams available in the conference. The application may also choose to send and stop sending its own audio-video stream to the conference over the same connection. The ooVoo SDK also enables an application to query the video conference for information, and get status updates when the conference environment changes, for example, when a user joins or leaves the conference.

## What is a Conference ID?

A Conference ID is a unique identifier assigned by you to each ooVoo video conference you create. In addition, the ooVoo Platform internally creates a globally unique identifier to be associated with each Conference ID you register with ooVoo.

## What is a Participant?

A Participant in an ooVoo Video Conference is a user who has successfully connected to the conference session. A participant may receive any or all audio video streams in the conference, as well as sending its own audio and video streams into the conference. You can control which audio video streams a participant can send or receive.

## What is a Participant ID?

A Participant ID is a unique identifier assigned by the ooVoo video service for each participant in an ooVoo video conference, upon a user’s successful connection to the conference session.

## What is a Video Plugin?

Video plugins allow you to directly access the video pipeline and make changes to the frames. This is used to implements filters and video effects and other "post processing" elements to the video.
 

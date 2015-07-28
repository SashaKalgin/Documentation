# Android Sample Application QuickStart
<!-- MarkdownTOC -->

- [What is included in the ooVoo Video Chat SDK for Android download package?](#what-is-included-in-the-oovoo-video-chat-sdk-for-android-download-package)
- [Prerequisites](#prerequisites)
  - [Android Studio](#android-studio)
  - [Eclipse](#eclipse)
  - [How do I build and run the ooVoo sample app included in the SDK download package in Eclipse?](#how-do-i-build-and-run-the-oovoo-sample-app-included-in-the-sdk-download-package-in-eclipse)

<!-- /MarkdownTOC -->



## What is included in the ooVoo Video Chat SDK for Android download package?
The SDK package contains the following items:
- docs
  - ooVooSdk-doc.jar: Javadoc documentation of public APIs exposed by the SDK
  - Developer Guide PDF (this doc)

- libs
  - armeabi-v7a : shared object library for ARM platform
  - x86 : shared object library for x86 platform
  - oovooSdk.jar : ooVoo SDK jar file

- SampleApp: the complete source project bundle of a sample multi-party video chat application built with the ooVoo SDK.

# Prerequisites
You will need either Android Studio or Eclipse with ADT, Android SDK.

## Android Studio
**Step #1**

Open ooVooSample project in Android Studio, by choosing Open existing Android Studio project:

![enter image description here](http://code.oovoo.com/native/docs/android/androidstudio_sample/1.png)

**Step #2**

Select the path to the ooVoo SDK bundle -> ooVooSample:

![enter image description here](http://code.oovoo.com/native/docs/android/androidstudio_sample/2.png)

**Step #3**

Review the project tree:

![enter image description here](http://code.oovoo.com/native/docs/android/androidstudio_sample/3.png)

**Step #4**

Embed your Application token you created on the [ooVoo Developers dashboard](https://developer.oovoo.com) into the _ApplicationSettings_ file:

![enter image description here](http://code.oovoo.com/native/docs/android/androidstudio_sample/4.png)

**Step #5**

Compile and run your project by clicking the "Run 'app'" button from the top menu:

![enter image description here](http://code.oovoo.com/native/docs/android/androidstudio_sample/5.png)

**Step #6**

Select your connected device (or emulator):

![enter image description here](http://code.oovoo.com/native/docs/android/androidstudio_sample/6.png)

> Note: Make sure the enable "_Use Host GPU_" setting in the under the _"Emulation Options"_ in the Android Virtual Device Manager, otherwise, you may get an error regarding OpenGL.

> Note:We support writing logs to the SD card. Please make sure define a size for your SD card so that can use it for logging if you wish.

> Note: Make sure you have selected "Emulated" for front and back camera. Otherwise, you will not be able to simulate video from AVD.

## Eclipse
## How do I build and run the ooVoo sample app included in the SDK download package in Eclipse?
**Step #1**

Open Eclipse and select the file menu to import the ooVoo sample app project:

![enter image description here](http://code.oovoo.com/native/docs/android/Eclipse_SampleApp/1.png)

**Step #2**

From the "Import" screen pop up, choose "Existing Android Code into Workspace" and click _next_:

![enter image description here](http://code.oovoo.com/native/docs/android/Eclipse_SampleApp/2.png)

**Step #3**

Browse to the folder where you downloaded the SDK to and select the "libs" folder and then copy the "_\libs_" folder and related sub-folders from the ooVoo SDK distribution into your application folder.

![enter image description here](http://code.oovoo.com/native/docs/android/Eclipse_SampleApp/3.png)

**Step #4**

You should get the following project tree view, (refresh your project to see the "\libs" folder):

![enter image description here](http://code.oovoo.com/native/docs/android/Eclipse_SampleApp/4.png)

**Step #5**

Embed your Application token you have been created on ooVoo dashboard into ApplicationSettings file

![enter image description here](http://code.oovoo.com/native/docs/android/Eclipse_SampleApp/4.5.png)

**Step #6**

Right Click on the Project name and choose "Run As->Android Application"

![enter image description here](http://code.oovoo.com/native/docs/android/Eclipse_SampleApp/5.png)

> Note: Make sure the enable "**Use Host GPU**" setting in the under the "**Emulation Options**" in the Android Virtual Device Manager, otherwise, you may get an error regarding OpenGL.

> Note: As of SDK v1.4 we now support writing logs to the SD card. Please make sure define a size for your SD card so that can use it for logging if you wish.

![enter image description here](http://code.oovoo.com/native/docs/android/14_SD_card.png)

To authenticate, you can either pre-populate the AndroidManifest.XML file in the root project folder with your App Token, Back-end Url and ConferenceID or when "ooVooSample" is running on your device, go into the App settings fill in the four empty fields on the main screen in order to create or join an ooVoo video conference:
- "**Application ID**" – provided to you by ooVoo
- "**Application Token**" – provided to you by ooVoo
- "**Conference ID**" – the name of the ooVoo video conference you want to join. If this is a new name under a specific Application ID a new conference will be created and you will be the first participant in the conference. To have other "**ooVooSample**" users join the conference, simply have them enter the same Conference ID string.
- "**Display Name**" – a string that you want to be displayed under your video when viewed by other participants.

Hit the "**Join**" button and enjoy!

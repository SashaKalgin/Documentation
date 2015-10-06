# Changelog for Version 2.1
## Major Changes in this Release
- iOS9 compatibility
- Android minimal version supported 4.0 and devices with NEON 
- New camera states : On/Off/Paused (Paused in SlideOver in iOS9)
- All classes in iOS have been renamed with prefix "ooVoo" to avoid name collisions
- Typo fixes in API
- 3rd party libraries
	- OpenSSL upgraded to latest 1.0.2d
	- Boost upgraded to latest 1.59
	- Opus upgraded to latest 1.1.1
	- VP8 upgraded to latest 1.4.0


## List of all changes for iOS
- Changes in ooVooClient Interface
	- New: getSdkVersion
	- New: updateConfig
	- Changes in Properties
		- New: setSslVerifyPeer
		- New: isSslVerifyPeer
		- New: app_token
- Changes in ooVooAccount Protocol
	- Properties
		- New: delegate
	- Changes in ooVooAccountDelegate Protocol
		- New: didAccountLogIn
		- New: didAccountLogOut
- Changes in ooVooAVChat Protocol
	- New: registerPlugin
	- New: unregisterPlugin
	- New: getUserFullName
	- New: isResolutionSupported
	- Properties
		- New: isInCallMessagePermit
	- ooVooAVChatDelegate
		- New: didConferenceError
		- New: didNetworkReliabilityChange
- Changes in ooVooVideoController Protocol
  - New: sizeToCameraResolutionLevel
 	- Properties
		- New: getActiveDevice
		- New: setActiveDevice
    - ooVooVideoControllerDelegate Protocol
  		- Removed: didActiveDeviceChanged
- Changes in ooVooAudioController Protocol
	- New: unInitAudio
	- Removed: getRecorderDevicesList
	- Removed: getPlaybackDevicesList
  - AudioControllerDelegate
		- Removed: didActiveDeviceChanged
		- Removed: didAudioDeviceStateChanged
	- Removed: AudioControllerConfigKey
- New: ooVooVideoDevice Protocol
	- isResolutionSupported
	- isFront
	- getAvailableResolutions
- New: ooVooParticipant Protocol
	- Properties
		- participantID
		- type
- New: Enumerators
	- ooVooDeviceState
	- ooVooAudioRouteType
	- ooVooVideoControllerConfigKey
	- ResolutionLevel
	- ooVooPstnState
	- ooVooAudioControllerConfigKey
	- ooVooAVChatState
	- ooVooAVChatRemoteVideoState
	- ooVooAVParticipantType

## List of all changes for Android
- Changes in ooVooClient
	- New: isAuthorized
	- New: isDeviceSupported
- New: Device
	- getID
	- getName
- Effect
	- getCategory
	- getIconUrl
	- getID
	- getName
	- getPurchaseId
- Changes in PluginFactory
	- createPluginInstance
- Changes in AVChat
	- ConferenceState
	- Rename: sendData to send
	- New: unregisterplugin
- Changes in AudioController
	- AudioRouteMode
	- uninitAudio
- Changes in AudioRoute
	- getName
	- getRouteId
	- isActive
- Changes in AudioRouteController
	- getRoutes
	- setListener
	- setRoute
	- Changes in AudioRouteControllerListener
		- onAudioRouteChanged
- Changes in VideoController
	- Rename: ResolutionLevel
	- VideoConfigKey
	- getConfig
	- setConfig
- Changes in VideoControllerListener
	- Removed: onAvailableResolutionInCallChanged
- Changes in VideoDevice
	- getAvailableResolutions
	- isResolutionSupported


# Changelog for Version 2.0
## Major Changes in this Release
- This is a major version release, breaking API compatibility in some cases
- Major refactoring and addition of a new extensible API that makes it easier to add features
- Maintains full interoperability with v1.x (legacy clients are not forced to upgrade)

## Features
- Added framework to support video plugins – filters, effects, sources and sinks
- Hardware accelerated video on iOS and lower CPU usage
- Greatly improved audio quality and lower end to end delay
-

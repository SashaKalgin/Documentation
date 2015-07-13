# Developing Plugins
<!--MarkdownTOC-->

- [Introduction to Plugins](#introduction-to-plugins)
- [Plugin Workflow](#plugin-workflow)
- [Data Storage Types](#data-storage-types)
    - [video_data](#video_data)
    - [video_frame](#video_frame)
- [Plugin APIs](#plugin-apis)
    - [Factory Interfaces](#factory-interfaces)
- [Plugin Interfaces](#plugin-interfaces)
    - [Video Capture Plugin](#video-capture-plugin)
    - [Video Effect Plugin](#video-effect-plugin)
    - [`plugin` and `plugin_info`](#plugin-and-plugin_info)
        - [`plugin`:](#plugin)
        - [`plugin_info`](#plugin_info)
- [Appendix A: iOS sample](#appendix-a-ios-sample)
    - [Implement plugins APIs](#implement-plugins-apis)
    - [Wrap your factory for iOS](#wrap-your-factory-for-ios)
    - [Implement video effect](#implement-video-effect)
    - [Import and register your plugin in application](#import-and-register-your-plugin-in-application)
    - [Call your plugin](#call-your-plugin)
- [Appendix B: Android sample](#appendix-b-android-sample)
    - [Implement plugins APIs](#implement-plugins-apis-1)
    - [Wrap your factory for Android](#wrap-your-factory-for-android)
    - [Implement video effect](#implement-video-effect-1)
    - [Import and register your plugin in application](#import-and-register-your-plugin-in-application-1)
    - [Call your plugin](#call-your-plugin-1)

<!--/MarkDownTOC-->
## Introduction to Plugins
Video Plugins enable you to gain direct access to the video pipeline and manipulate the video stream. They allow you to access the video frame by frame and process each frame. This enables adding "post processing" elements to the video and adding logic to your application based on data from within the video pipeline, such as filters and video effects (background replacement, avatars, etc).

# Plugin Workflow

![Plugin Workflow Diagram](https://CODE.OOVOO.COM/native/docs/android/plugin-workflow.PNG)

# Data Storage Types

##	video_data

**`video_data`** is the structure that stores video data information while it passes from capture to plugin or from plugin further down the video pipeline. It contains only the pixels, without any additional metadata like timestamp, frame number, orientation etc.

|Method|Description|
|------|------|
|`uint16_t width()`| Width of frame in pixels|
|`uint16_t height()`|Height of frame in pixels|
|`color_format format()`| Pixel format of video frame - YV12, NV12, RGB32 etc.|
|`int num_planes()`|Number of planes contained in frame|
|`void* plane_ptr(const int num)`|Raw data of the plane, in byte array|
|`int plane_pitch(const int num)`|Size of plane, in bytes|

##	video_frame

**`video_frame`** is the structure which is used to store the video frame information. It contains `video_data` as a member.

|Method|Description|
|------|------|
|`video_data::ptr video_data()`||
|`video_type type()`|UNCOMPRESSED, H264, VP8 etc.|
|`color_format format()`|YV12, NV12, RGB32 etc.|
|`unsigned int texture()`|Specifies the name of a texture only for render|
|`uint16_t width()`||
|`uint16_t height()`||
|`uint16_t frame_number()`||
|`uint64_t time()`|Time of capture as reported by capture device (or closest to that, depending on platform)|
|`bool key_frame()`|True if this frame is a reference frame (relevant to frames of type H264 and VP8)|
|`bool mirror()`|True if frame is mirrored relative to captured image|
|`int rotation_angle()`|Angle that this frame is rotated relative to "straight up" orientation|
|`int device_rotation_angle()`|Device orientation at the moment of capture|

# Plugin APIs

##	Factory Interfaces

Plugins are implemented through "factories." Create a factory which is used to register your plugin with the SDK.  Your factory should inherit from **`plugin_factory`** in **`plugins.h.`** One factory can be used to manage one or multiple plugins.

|			Method|		Description|
|-------------|--------------------------------------|
|`plugin::ptr create_plugin_instance(plugin_info::ptr info);`|Create your plugin instance.  Your plugin instance will be passed to the ooVoo sdk when the register process is triggered|
|`sdk_error load(plugin_registrator::ptr registrator);`|Will be called by the SDK when a factory is registed/unregisted|
|`sdk_error unload();`|Will be called by the SDK when factory is registed/unregisted|
|`const char* name() const;`|Provide factory info by implementing the following interfaces|
|`const char* version() const;`|Provide factory info by implement the following interfaces|

# Plugin Interfaces

Implement the ooVoo plugin interface defined in video **`_plugin.h.`**

##	Video Capture Plugin

I.	Inherit `video_capture`, e.g. `OOVOO_CLASS(VideoCapture3DSeg, ooVooSdk::video_capture, "{b42c0637-d64b-441a-bb92-fff9f315cba9}");`

|			Method					|		Description|
|---------------------|--------------|
|`void set_listener(video_capture_listener::ptr handler);`|Set video_capture_listener to your capture plugin.   The listener is used to deliver video frames to the preview and the encoder.  This function will be called by the SDK|
|`sdk_error set_output_format(const video_type& type, const color_format& format);` |Notify the output video format|
|`sdk_error set_preview_format(const color_format& format);`|Notify the preview output video format|
|`sdk_error start(const int width, const int height, const int fps);`|Called when capture starts|
|`sdk_error stop();`|Called when capture stops|
|`sdk_error effect(video_effect::ptr effect);`|Give capture access to effect|
|`video_effect::ptr effect() const;`|Return the effect which we set to capture back to pipeline|


II.	Inherit `media_device`:

|			Method		|		Description|
|---------------|--------------|
|`sdk_error hold(const char* reason);`|Called when capture is paused|
|`sdk_error unhold();`|Called when capture is resumed|
|`void set_state_listener(media_device_state_listener::ptr handler);`|Set the listener for the response of different device status|

III.	`video_capture_listener:` In the capture thread, the plugin should call `on_output_frame` and `on_preview_frame` from `video_capture_listener` to deliver the captured frame to the SDK pipeline (for preview and sending to the conference)


    listener->on_output_frame(pFrame, true);
    listener->on_preview_frame(pFrame);

##	Video Effect Plugin

Inherit the `video_effect`, e.g. `OOVOO_CLASS(EffectPlugin, ooVooSdk::video_effect, "{bc06d2ef-c2d1-4190-9f41-c58b5603535d}")`  

|			Method					|		Description|
|---------------------|--------------|
|`video_frame::ptr process(video_frame::ptr frame);`|Actual processing method of the video effect called by SDK for each frame arriving from capture device before sending it to the encoder. The input frame is the raw frame received from the capture component. Return value is the processed frame in the same video_frame format.|

##	`plugin` and `plugin_info`

You also need to implement the interfaces `plugin` and `plugin_info` for all your plugins. These classes provide basic information about plugins too SDK.

### `plugin`:

|			Method					|		Description|
|---------------------|--------------|
|`const char* instance_id()`|Unique id of the plugin instance. Plugins are referenced by their id in other APIs|

### `plugin_info`

|			Method					|		Description|
|---------------------|--------------|
|`Type  type() const`|EFFECT, VIDEO_CAPTURE etc.|
|`const char* id() const`|ID of the plugin. See `plugin` interface|
|`const char* internal_id() const`||
|`const char* display_name() const`|Human readable string available to application developer or presented in UI and names or describes the plugin. For example: "Black and white filter"|
|`object_ptr<plugin_factory> factory() const`|Returns reference to plugin factory that created and owns the instance of plugin|
|`State state()`|Returns the plugin state. For example, TURNING_ON, TURNING_OFF, ON_HOLD, etc. |
|`void  state(const State s)`|Set current plugin state|
|`const char* parameters()`|Returns current parameters of the plugin in JSON format. For example, "{"hue"="0.6"}"|
|`void parameters(const char* json_params)`|Set initial plugin parameters which are passed to plugin during creation|
|`void update_parameters(const char* json_params)`|This method allows updating plugin parameters in real-time for active plugin. For example, "{"hue"="0.7"}"|
|`bool is_default() const`|This method is relevant to plugins that implement device but not effect. If it is true then the SDK will use this device when there is no other device selected|

# Appendix A: iOS sample

## Implement plugins APIs

 - Implement `oovoo::sdk::plugin_factory` class which will interact with the SDK and be the container and creator for plugins themselves.


    class EffectSampleFactory : public oovoo::sdk::plugin_factory
    {
     ...
    }


##	Wrap your factory for iOS

 - Import `<ooVooSdk/ooVooAVChat.h>`
 - Implement you own objective-c class derived from protocol plugin_factory


    #import <ooVooSdk/ooVooAVChat.h>

    @interface PluginWrapper : NSObject <ooVooPluginFactory>
    -(void*) getooVooPluginFactoryNative;
    @end

## Implement video effect


    class EffectPlugin : public oovoo::sdk::video_effect
    {
      ...
    }


## Import and register your plugin in application

 - Import your platform factory wrapper
 - Register your plugin factory wrapper with ooVoo SDK


    PluginWrapper* pl_wrapper = [[PluginWrapper alloc] init ];
    [self.sdk.AVChat registerPlugin: pl_wrapper];


## Call your plugin

Now, when you call `getEffectsList()` in `VideoController` you will get your video effect.



# Appendix B: Android sample

## Implement plugins APIs

 - Implement `oovoo::sdk::plugin_factory` class which will interact with SDK and be the container and creator for plugins themselves.


    class EffectSampleFactory : public oovoo::sdk::plugin_factory
    {
     ...
    }


##	Wrap your factory for Android

 - Import `com.oovoo.sdk.interface.AVChat`
 - Implement you own objective-c class derived from protocol plugin_factory




## Implement video effect


    class EffectPlugin : public oovoo::sdk::video_effect
    {
      ...
    }


## Import and register your plugin in application

 - Import your platform factory wrapper
 - Register your plugin factory wrapper with ooVoo SDK


    import `com.yourcompany.plugin.ooVooPluginFactory;
    ...
    ooVooPluginFactory factory = new  ooVooPluginFactory();
    ooVooClient.sharedInstance().getAVChat().registerPlugin(factory);


## Call your plugin

Now, when you call `getEffectsList()` in `VideoController` you will get your video effect.

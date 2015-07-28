# Eclipse and Android Studio Integration Guide
<!-- MarkdownTOC -->

- [Eclipse Integration](#eclipse-integration)
- [Android Studio Integration](#android-studio-integration)

<!-- /MarkdownTOC -->



# Eclipse Integration
> Important: Support for the Android Developer Tools (ADT) in Eclipse is ending, per [Google's announcement](http://android-developers.blogspot.com/2015q/06/an-update-on-eclipse-android-developer.html). You should migrate your app development projects to Android Studio as soon as possible. For more information on transitioning to Android Studio, see [Migrating to Android Studio](http://developer.android.com/sdk/installing/migrate.html).

**Step #1**

Create a new android project by following the default project settings:

![Eclipse](https://code.oovoo.com/native/docs/android/android_dev_guide/1.png)

**Step #2**

Create a MyApp  android project with default preset:

![enter image description here](https://code.oovoo.com/native/docs/android/android_dev_guide/3.png)

**Step #3**

If it doesn't exist, create a directory named `libs` in the root directory of the project and copy the following files into it:
- armeabi-v7a
- x86
- oovoosdk.jar

![https://code.oovoo.com/native/docs/android/android_dev_guide/4.png](https://code.oovoo.com/native/docs/android/android_dev_guide/4.png)

**Step #4**

Open your project properties select **_Java Build Path_** and **_Libraries_** and add the _oovoosdk.jar_ from your libs folder in order to link it:

![enter image description here](https://code.oovoo.com/native/docs/android/android_dev_guide/5.png))

**Step #5**

Create MyApplication class:

![enter image description here](https://code.oovoo.com/native/docs/android/android_dev_guide/6.png)

**Step #6**

Register MyApplication class in AndroidManifest.xml: ![enter image description here](https://code.oovoo.com/native/docs/android/eclipse/6.png)

**Step #7**

Add the following permissions into your project manifest : AndroidManifest.xml

```java
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS"/>
<uses-permission android:name="android.permission.RECORD_AUDIO"/>
<uses-permission android:name="android.permission.RECORD_VIDEO"/>
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.CAMERA"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
<uses-permission android:name="android.permission.READ_PHONE_STATE"/>
<uses-permission android:name="android.permission.PROCESS_OUTGOING_CALLS"/>
<uses-permission android:name="android.permission.BLUETOOTH"/>
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN"/>
<uses-permission android:name="android.permission.BLUETOOTH_PRIVILEGED"/>
```

![https://code.oovoo.com/native/docs/android/eclipse/7.png](https://code.oovoo.com/native/docs/android/eclipse/7.png)

**Step #8**

Add the following code for SDK initializion and low level logs enabling.

```java
import android.app.Application;

import com.oovoo.core.LoggerListener;
import com.oovoo.sdk.api.ooVooClient;

/**
 * Created by developer on 7/6/15.
 */
public class MyApplication extends Application implements LoggerListener{

    @Override
    public void onCreate(){
        super.onCreate();

        ooVooClient.setContext(this);
        ooVooClient.setLogger(this,LogLevel.Trace);
    }

    @Override
    public void OnLog(LogLevel logLevel, String s, String s1) {

        //Implement your log dispatching here
    }
}
```

![enter image description here](https://code.oovoo.com/native/docs/android/eclipse/8.png)

# Android Studio Integration
**Step #1**

Create a new project, choose _Start New Android Studio Project_

![https://code.oovoo.com/native/docs/android/androidstudio/1.png](https://code.oovoo.com/native/docs/android/androidstudio/1.png)

**Step #2**

Choose your Application name and company domain and click next.

![https://code.oovoo.com/native/docs/android/androidstudio/2.png](https://code.oovoo.com/native/docs/android/androidstudio/2.png)

**Step #3**

Build a new class called MyApplication.
- Right click on the package name
- Create new java class

![https://code.oovoo.com/native/docs/android/androidstudio/3.png](https://code.oovoo.com/native/docs/android/androidstudio/3.png)

**Step #4**

Import ooVoosdk.jar into your new project

 Create new folder called `libs`, and copy `oovooSdk.jar` from the SDK bundle.

![https://code.oovoo.com/native/docs/android/androidstudio/4.png](https://code.oovoo.com/native/docs/android/androidstudio/4.png)

**Step #5**

Click on "sync project with Gradle files" button, in order to link `oovooSdk.jar` with your project.

![https://code.oovoo.com/native/docs/android/androidstudio/5.png](https://code.oovoo.com/native/docs/android/androidstudio/5.png)

**Step #6**

Build a new Java Class.

Right click on package name, choose _New -> Java Class_ , and _extends Application_ class.

```java
import android.app.Application;

/**
 * Created by developer on 7/6/15.
 */
public class MyApplication extends Application{

}
```

![https://code.oovoo.com/native/docs/android/androidstudio/6.png](https://code.oovoo.com/native/docs/android/androidstudio/6.png)

**Step #7**

Update the manifest file configuration with the code below:

```java
android:name=".MyApplication"
```

![https://code.oovoo.com/native/docs/android/androidstudio/7.png](https://code.oovoo.com/native/docs/android/androidstudio/7.png)

**Step #8**

Add the following permissions into your project manifest : AndroidManifest.xml

```xml
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS"/>
<uses-permission android:name="android.permission.RECORD_AUDIO"/>
<uses-permission android:name="android.permission.RECORD_VIDEO"/>
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.CAMERA"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
<uses-permission android:name="android.permission.READ_PHONE_STATE"/>
<uses-permission android:name="android.permission.PROCESS_OUTGOING_CALLS"/>
<uses-permission android:name="android.permission.BLUETOOTH"/>
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN"/>
<uses-permission android:name="android.permission.BLUETOOTH_PRIVILEGED"/>
```

![https://code.oovoo.com/native/docs/android/androidstudio/8.png](https://code.oovoo.com/native/docs/android/androidstudio/8.png)

**Step #9**

Add the following code for SDK initializion and to enable low level logs enable.

```java
package com.example.myapplication;

import android.app.Application;

import com.oovoo.core.LoggerListener;
import com.oovoo.sdk.api.ooVooClient;

/**
 * Created by developer on 7/6/15.
 */
public class MyApplication extends Application implements LoggerListener{

    @Override
    public void onCreate(){
        super.onCreate();

        ooVooClient.setContext(this);
        ooVooClient.setLogger(this,LogLevel.Trace);
    }

    @Override
    public void OnLog(LogLevel logLevel, String s, String s1) {

        //Implement your log dispatching here
    }
}
```

![https://code.oovoo.com/native/docs/android/androidstudio/9.png](https://code.oovoo.com/native/docs/android/androidstudio/9.png)

# LowPowerMobile for Android

*其他语言版本： [简体中文](README.zh.md)*

The OpenLive for Android Sample App is an open-source demo that will help you get live video broadcasting integrated for Moible directly into your Android applications using the Agora Video SDK.

With this sample app, you can:

- Join / leave channel
- Mute / unmute audio


## Running the App
First, create a developer account at [Agora.io](https://dashboard.agora.io/signin/), and obtain an App ID. Update "app/src/main/res/values/strings_config.xml" with your App ID.

```
<string name="private_app_id"><#YOUR APP ID#></string>
```

Way to integrate:

First, download the **Agora Video SDK** from [Agora.io SDK](https://www.agora.io/en/download/). Unzip the downloaded SDK package and copy ***.jar** under **libs** to **app/libs**, **arm64-v8a**/**x86**/**armeabi-v7a** under **libs** to **app/src/main/jniLibs**.

Then, add the fllowing code in the property of the dependence of the "app/build.gradle":

```
compile fileTree(dir: 'libs', include: ['*.jar'])
```

Finally, open project with Android Studio, connect your Android device, build and run.

Or use `Gradle` to build and run.

##Matters needing attention
- The audio format needs to be consistent with the watch or other IOT devices set in the code.
- joinchannel the channel name corresponding to the function can be modified by itself.
- Coding resolution frame rate, customized changes, opponents table end, it is not appropriate to set too large.  DEfault: mRtcEngine.setVideoProfile((160,120,15,120));

## Developer Environment Requirements
- Android Studio 2.0 or above
- Real devices (Nexus 5X or other devices)
- Some simulators are function missing or have performance issue, so real device is the best choice

## Connect Us
- You can find full API document at [Document Center](https://docs.agora.io/en/)
- You can file bugs about this demo at [issue](https://github.com/AgoraIO/OpenLive-Android/issues)

## License
The MIT License (MIT).

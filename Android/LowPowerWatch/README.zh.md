# LowPowerWatch for Android Watch

*Read this in other languages: [English](README.en.md)*

这个开源示例项目演示了智能手表如何快速集成 Agora 视频 SDK，实现多人视频连麦直播。

在这个示例项目中包含了以下功能：

- 加入通话和离开通话；
- 静音和解除静音；


## 运行示例程序
首先在 [Agora.io 注册](https://dashboard.agora.io/cn/signup/) 注册账号，并创建自己的测试项目，获取到 AppID。将 AppID 填写进 "app/src/main/res/values/strings_config.xml"

```
<string name="private_app_id"><#YOUR APP ID#></string>
```

集成方式：

第一步: 在 [Agora.io SDK](https://www.agora.io/cn/download/) 下载 **视频通话 + 直播 SDK**，解压后将其中的 **libs** 文件夹下的 ***.jar** 复制到本项目的 **app/libs** 下，其中的 **libs** 文件夹下的 **arm64-v8a**/**x86**/**armeabi-v7a** 复制到本项目的 **app/src/main/jniLibs** 下。

第二步: 在本项目的 "app/build.gradle" 文件依赖属性中添加如下依赖关系：

```
compile fileTree(dir: 'libs', include: ['*.jar'])
```

最后用 Android Studio 打开该项目，连上设备，编译并运行。

也可以使用 `Gradle` 直接编译运行。

##注意事项
- 针对手表的SDK是我们单独提供的SDK，特殊定制的，需要联系我们的商务获取对应的SDK
- 音频格式需要按照代码中设置的
- joinchannel 函数对应的频道名，可自行修改 。当前默认是：mRtcEngine.joinChannel(null, "yourchannel", "Extra Optional Data", 0);
- 编码分辨率帧率，可定制化修改，对手表端来说，不宜设置太大。  当前默认是：mRtcEngine.setVideoProfile(160, 120, 10, 120);

##IOT手表适配问题FAQ：
1.Q：手表支持硬编还是软编？
   A：手表定制的SDK是用硬编方式。
2.Q：手表这边推荐的编码分辨率是多少？
  A：推荐手表编码videoProfile 设置（160,120,10,120），建议手机端也同样设置
3.Q：手表硬件要求
  A：Android 4.4以上的系统，CPU 800M主频以上，内存 512M以上
4.Q：手表SDK和标准SDK区别
  A：手表SDK是定制的，做了很多功耗优化，专门为低功耗设备定制
5.Q：手表SDK和demo哪里下载
  A：手表SDK，需要联系我们的商务下载。demo：            https://github.com/AgoraIO/ARD-Agora-RTC-Low-Power/tree/master/Android
6.Q：功耗情况如何
  A：不同硬件设备会有不同，具体还需测试

## 运行环境
- Android Studio 2.0 +
- 真实 Android 设备 (Nexus 5X 或者其它设备)
- 部分模拟器会存在功能缺失或者性能问题，所以推荐使用真机

## 联系我们
- 完整的 API 文档见 [文档中心](https://docs.agora.io/cn/)
- 如果在集成中遇到问题, 你可以到 [开发者社区](https://dev.agora.io/cn/) 提问
- 如果有售前咨询问题, 可以拨打 400 632 6626，或加入官方Q群 12742516 提问
- 如果需要售后技术支持, 你可以在 [Agora Dashboard](https://dashboard.agora.io) 提交工单
- 如果发现了示例代码的 bug, 欢迎提交 [issue](https://github.com/AgoraIO/OpenLive-Android/issues)

## 代码许可
The MIT License (MIT).

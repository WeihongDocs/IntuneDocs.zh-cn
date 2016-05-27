---
# required metadata

title: 决定如何使用 Microsoft Intune 为移动应用程序管理准备应用 | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 决定如何使用 Microsoft Intune 为移动应用程序管理准备应用
可以使用 Intune 应用包装工具或 Intune App SDK 来启用你的应用以使用移动应用程序管理策略。 通过此信息了解这两种方式以及何时使用这两种方式。

## Intune 应用包装工具
应用包装工具主要用于内部业务线 (LOB) 应用。 此工具是一个命令行应用程序。它可以在应用周围创建包装器，之后包装器将允许 Intune 移动应用程序管理策略管理该应用。 使用此工具不需要源代码，但需要签名凭据。  有关签名凭据的详细信息，请参阅 [Intune 博客](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx)。 若要获取应用包装工具文档，请参阅 [Android 应用包装工具](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)和 [iOS 应用包装工具](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

应用包装工具不支持应用商店或 Play Store 中的应用，也不支持需要开发时间集成的功能（请参见以下功能对比表）。

如果已编写应用或者如果源代码不可用，则应该使用应用包装工具，而不是 SDK。

## Intune App SDK
App SDK 主要面向在应用商店或 Play Store 中安装了应用并想使用 Intune 管理应用的客户。 但是，任何应用都可以集成 SDK，即使是 LOB 应用。

若要集成 SDK，需要对应用源代码具有访问权限。 有关集成 SDK 的说明，请参阅 [Microsoft Intune App SDK](https://msdn.microsoft.com/library/mt627769.aspx).

## 功能比较
此表列出了可用于 App SDK 和应用包装工具的设置。

> [!NOTE]
> 应用包装工具可以与独立 Intune 或带 Configuration Manager 的 Intune 结合使用。

|功能|App SDK|应用包装工具|
|-----------|---------------------|-----------|
|限制显示在企业托管浏览器内的 Web 内容|X|X|
|阻止 Android、iTunes 或 iCloud 备份|X|X|
|允许应用向其他应用传送数据|X|X|
|允许应用从其他应用接收数据|X|X|
|限制剪切、复制和粘贴到其他应用程序|X|X|
|访问需要简单 PIN|X|X|
|使用 Intune PIN 替换内置应用 PIN|X||
|指定重置 PIN 前的尝试次数|X|X|
|需要指纹而不是 PIN（仅限 iOS设备）<br></br>**注意：**只在仅 MAM 环境下可用|X||
|访问需要公司凭据|X|X|
|阻止在已越狱或取得 root 权限的设备上运行托管应用|X|X|
|加密应用数据|X|X|
|在指定分钟数后重新检查访问要求|X|X|
|指定离线宽限期|X|X|
|阻止屏幕捕捉（仅限于 Android 设备）|X|X|
|完全擦除|X|X|
|选择性擦除 <br></br>**注意：**对于 iOS 设备，删除管理配置文件时，也会删除该应用。|X||
|防止“另存为” |X||
|支持多身份标识|X||

### 另请参阅
[Android 应用包装工具](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS 应用包装工具](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[使用 SDK 启用针对移动应用程序管理的应用](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<!--HONumber=May16_HO1-->


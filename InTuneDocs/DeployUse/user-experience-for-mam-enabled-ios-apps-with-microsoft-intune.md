---
title: "用于 MAM 策略的 iOS 应用 | Microsoft Intune"
description: "本主题介绍 iOS 应用由移动应用管理策略托管时会出现的情况。"
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 3f9d9c7cafcdac0db21e5ba35f713fe630c65b99


---

# iOS 应用由 MAM 策略托管时会出现的情况
 本主题描述具有 MAM 策略的应用的用户体验。 仅当在工作环境中使用应用（例如使用工作帐户访问应用，或访问存储在公司 OneDrive for Business 位置的文件）时，才应用移动应用管理 (MAM) 策略。
##  访问应用

如果设备**未在 Intune 中注册**，则最终用户首次使用应用时需要重启该应用。  必需重启才能将 MAM 策略应用到该应用。 以下屏幕截图使用 Skype 应用对此进行解释：


![显示 PIN 提示的 iOS 设备的屏幕截图](../media/appmanagement/iOS_AppPINPrompt.png)

对于**在 Intune 中注册用于托管**的设备，最终用户将看到一条消息，提示应用目前已托管：

![iOS 设备的屏幕截图，其中 PIN 提示显示“由公司托管”消息](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  使用具有多身份支持的应用

使用应用时，仅在工作环境中应用 MAM 策略仅，因此根据工作或个人环境，应用可能有不同的行为。  

对于支持多身份的应用，仅当最终用户在工作环境中使用该应用时，Intune 才应用 MAM 策略。  例如，最终用户访问工作数据时将收到 PIN 提示。  对于 **Outlook 应用**，将在最终用户启动应用时提示其输入 PIN。 对于 **OneDrive 应用**，将在最终用户键入工作帐户时进行提示。  对于 Microsoft **Word**、**PowerPoint*和 **Excel**，将在最终用户访问存储在公司 OneDrive for Business 位置的文档时进行提示。
##  在设备上管理用户帐户

Intune 仅支持对于每个设备，将 MAM 策略部署到一个用户帐户。

* 根据所使用的应用，第二个用户可能会也可能不会在设备上受阻。 但是在所有情况下，只有获取 MAM 策略的第一个用户才会受该策略影响。
  * “Microsoft Word”、“Excel”和“PowerPoint”不会阻止第二个用户帐户，但第二个用户帐户不受 MAM 策略影响。  

  * 对于“OneDrive 和 Outlook 应用”，只能使用一个工作帐户。  将阻止在这些应用中添加多个工作帐户。  但是，你可以在设备上删除用户并添加其他用户。

* 如果设备在部署 MAM 策略之前具有现有的多个用户帐户，则 MAM 策略部署到的帐户首先由 Intune MAM 策略管理。


阅读以下示例方案以更深入地了解如何处理多个用户帐户。

用户 A 为两家公司（“X 公司”和“Y 公司”）工资。用户 A 对于每家公司具有一个工作帐户，它们都使用 Intune 来部署 MAM 策略。 **X 公司**在**Y 公司****之前**部署 MAM 策略。与“X 公司”关联的帐户会获得 MAM 策略，而与 Y 公司关联的帐户不会。如果你希望与 Y 公司关联的用户帐户通过 MAM 策略管理，则必须删除与 X 公司关联的用户帐户。
### 添加第二个帐户

如果使用 iOS 设备，则在同一设备上尝试添加第二个工作帐户时，可能会看到拦截消息。  随即显示帐户，可从中选择要删除的帐户。

![包含阻止消息以及“是”和“否”选项的对话框的屏幕截图](../media/AppManagement/iOS_SwitchUser.PNG)
## 后续步骤
[Android 应用由 MAM 策略托管时会出现的情况](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### 另请参阅
[使用 Microsoft Intune 创建和部署移动应用管理策略](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


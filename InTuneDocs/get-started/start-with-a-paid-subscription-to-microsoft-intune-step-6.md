---
title: "部署策略和应用 | Microsoft Intune"
description: "可以启用策略设置并部署将在设备注册到管理后立即应用的应用。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 56f7d1578ba6b193c6547686675e0fd4fde5f378


---

# <a name="create-policies-and-publish-apps"></a>创建策略并发布应用
在开始将应用注册到 Intune 之前，可以启用策略设置以及将会在这些设备进入管理后立即部署的应用。 Intune 策略提供的设置有助于控制移动设备上的安全设置、维护计算机的 Windows 防火墙和 Endpoint Protection 设置以及部署应用程序。 可以配置策略、添加应用并对这些应用进行部署，以便设备在 Intune 中注册后立即接收设置和应用。

策略和应用是特定于平台的。

## <a name="manage-device-settings"></a>管理设备设置

 设备策略设置是以每个平台基础进行配置和管理的。 可以为以下平台配置策略：

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android 和 Samsung KNOX 标准版](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10（电脑版和移动版）](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows 团队](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [运行 Intune 软件客户端的 Windows 电脑](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

可详细了解如何[使用 Microsoft Intune 策略管理设备上的设置和功能](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)。

## <a name="add-and-deploy-apps"></a>添加和部署应用

可以将应用添加到 Intune，然后通过两种方式将其部署到托管设备：
- **必需的安装** - 应用会自动将应用安装到托管设备
- **可用安装** - 应用将显示在 Intune 公司门户中，以便用户可以选择是否在其设备上安装它们

### <a name="add-apps"></a>添加应用

首先，必须通过以下方法之一使应用在 Intune 中可用：
- [为已注册设备添加应用](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [为 Intune 软件客户端电脑添加应用](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>部署应用

现在该应用已在 Intune 中可用，你可以将其部署到托管设备：
- [将应用部署到设备](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- 部署批量采购的应用：
    - [iOS - 批量采购计划](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [适用于企业的 Windows 应用商店](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](https://docs.microsoft.com/en-us/Intune/deploy-use/android-for-work-apps)

    配置应用以部署之后，可以[配置应用](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune)和[监视应用](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune)。

>[!div class="step-by-step"]

>[&larr; **组织用户和设备**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**自定义公司门户** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Dec16_HO2-->


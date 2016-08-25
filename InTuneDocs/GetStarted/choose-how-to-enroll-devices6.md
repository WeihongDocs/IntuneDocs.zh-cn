---
title: "选择如何注册移动设备 |Microsoft Intune"
description: "决定如何通过回答几个简单的问题在 Intune 中注册移动设备"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: f65bdbc7aa708b37a766275494e080436d9a5485
ms.openlocfilehash: 3e5c9ed2ba374172ea27b61a34f0746f582f0ebc


---
# 选择如何注册移动设备

你对这一系列问题的回答将帮助确定你管理的设备的最佳注册方法。

## **你将如何管理专用的 iOS 设备？**

  > [!div class="button"]
[iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)   [iOS 设置助理 >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [使用 IMEI 进行标记>](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  你可以使用专用用户注册公司拥有的设备，方法如下：

  - **Apple 的设备注册计划 (DEP)** - 通过 DEP 购买或管理的 iOS 设备可以面向注册配置文件。 当用户第一次开启他们的设备时，设备将下载 DEP 配置文件，并向 Intune 进行注册。

  - **Mac 上的 Apple Configurator** - Apple Configurator 是在 Mac PC 上运行的 Apple 应用程序。 你可以使用 USB 电缆将 iOS 设备连接到 Mac 以在设备上安装注册配置文件。 如果你愿意恢复设备的出厂设置对它们进行注册，请使用“设置助理”注册。

  - **使用 IMEI 号码进行标记** - 通过导入公司拥有的设备的国际移动设备标识 (IMEI) 号，你可以在 Intune 中将它们标记为公司拥有的设备。 然后，用户可以通过安装公司门户将其设备注册为个人设备，以访问公司资源（如电子邮件、应用和数据）。

  > [!div class="button"]
  [< 上一步](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO3-->


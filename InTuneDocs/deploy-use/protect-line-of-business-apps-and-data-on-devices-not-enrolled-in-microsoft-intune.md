---
title: "保护未注册设备上的 LOB 应用 | Microsoft Intune"
description: "本主题介绍如何准备自定义的业务线应用，以便应用可帮助防止数据丢失的移动应用管理策略。"
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 3bce8989944985c36a3d233fbb05d2f3f135b7e7


---

# <a name="protect-line-of-business-apps-and-data-on-devices-that-are-not-enrolled-in-microsoft-intune"></a>保护未在 Microsoft Intune 上注册的设备上的业务线应用和数据

移动应用管理 (MAM) 策略通过限制可能会泄漏公司数据的操作以及实施数据访问要求（如应用 PIN）来保护公司数据。 若要将 MAM 策略应用于 iOS 和/或 Android 业务线应用，首先必须使用 Microsoft Intune 应用包装工具包装此应用。 应用包装是一个将管理层应用于移动应用的过程，不要求对基础应用程序进行任何更改。 一旦应用包装完成，就可向其应用 MAM 策略并将其分发给最终用户。  

本主题说明将 MAM 策略应用于用户在**不受管理的员工自有设备**以及**由第三方移动设备管理 (MDM) 解决方案管理的设备**上访问的应用所需的步骤。  若要准备**已在 Intune MDM 中注册的设备**上运行的业务线应用，请参阅[决定如何使用 Microsoft Intune 为移动应用管理准备应用](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)。


##  <a name="step-1-prepare-the-app"></a>步骤 1：准备应用

将 MAM 策略应用于某个应用时，首先必须使用 [iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) 和 [Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) 版 Microsoft Intune 应用包装工具包装该应用，或者使用 [Intune 应用 SDK](/../develop/intune-app-sdk) 手动集成 Intune 应用保护功能。

若要深入了解应该使用应用包装工具还是 SDK，请参阅[决定如何使用 Microsoft Intune 为移动应用管理准备应用](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)。

## <a name="step-2-add-the-app"></a>步骤 2：添加应用

若要将业务线应用与 MAM 策略关联，必须按照以下步骤将应用详细信息添加至 Intune 订阅/租户：

1. 在 [Azure 门户](https://portal.azure.com/)中，转到“Intune 移动应用管理” > “设置”，然后选择“业务线应用”。

  ![包括业务线选项的“设置”边栏选项卡的屏幕截图](../media/mam-azure-portal-lob-on-settings.png)

2. 在“业务线应用”边栏选项卡中，选择“添加自定义应用”。

  ![“添加自定义应用”按钮位于顶部的“业务线应用”边栏选项卡的屏幕截图](../media/mam-azure-portal-add-lob-app-action.png)
3.  提供应用名称、应用标识符字段的捆绑标识符以及平台（iOS 或 Android）。

  ![“添加自定义应用”边栏选项卡的屏幕截图](../media/mam-azure-portal-add-app-details.png)

  此步骤可帮助创建唯一的应用列表。 租户 MAM 策略的目标应用列表中也会显示该应用，如下一步中所述。

## <a name="step-3-apply-mam-policies"></a>步骤 3：应用 MAM 策略
将应用元数据上传到服务后，应用列表中将显示该应用。 现可[创建新策略或使用现有策略](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)，并将其应用于步骤 2 中添加的业务线应用。

>[!IMPORTANT]
>必须将 MAM 策略定位给要使用已包装应用的用户。  未部署此策略的用户将无法使用该应用。


  ![显示有新业务线应用的“目标应用列表”边栏选项卡的屏幕截图](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a>步骤 4：分配应用
可通过以下方式将应用部署到用户：
* 对于在第三方 MDM 解决方案中注册的设备，可通过 MDM 解决方案分发应用。
* 对于不受任何 MDM 解决方案管理的设备，需要自定义解决方案。 用户必须在其设备上下载并安装应用。

## <a name="change-the-metadata"></a>更改元数据
如果需要更改应用详细信息（如应用名称或捆绑标识符），必须[删除应用](#remove-apps)，并[向其添加](#step-2-add-the-app)新的元数据。

##  <a name="remove-apps"></a>删除应用
可从应用列表中删除业务线应用。 这会从列表中删除该应用及与 MAM 策略的关联，但不会从用户设备中删除或卸载该应用。  

1.  在 [Azure 门户](https://portal.azure.com/)中，转到“Intune 移动应用管理” > “设置”。 在**设置**边栏选项卡上，选择**业务线**打开现有应用的列表。  
2.  选择要删除的应用，并选择“...”上下文菜单。

  ![含省略号的“业务线应用”边栏选项卡的屏幕截图](../media/mam-azure-portal-lob-context-menu.png)
3.  选择**删除应用程序**以删除该应用。

  ![含“删除应用程序”选项的“业务线”边栏选项卡的屏幕截图](../media/mam-azure-portal-delete-app.png)

  这会从业务线应用列表及 MAM 策略中的目标应用列表中删除该应用。



<!--HONumber=Nov16_HO5-->


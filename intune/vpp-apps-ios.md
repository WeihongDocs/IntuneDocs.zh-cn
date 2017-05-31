---
title: "管理 iOS 批量购买的应用 | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure 预览版：了解如何可以将从 iOS 应用商店中批量购买的应用同步到 Intune 中，然后管理并跟踪其使用情况。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3974145b4c244e251ee91a6216a79a6d8b1ad792
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>如何使用 Microsoft Intune 管理通过批量购买计划购买的 iOS 应用


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

iOS 应用商店允许你为想要在公司运行的应用购买多个许可证。 这有助于降低跟踪多个已购买应用副本的管理成本。

Microsoft Intune 可帮助你通过以下操作管理通过此计划购买的应用：从应用商店中导入许可证信息、跟踪已使用的许可证的数量，以及阻止安装超出你所拥有的应用的更多副本。

此外，可以与 Intune 同步、管理和分配从 Apple 批量采购计划应用商店购买的书，并将其分配给用户。 使用 Intune 门户中的 **Books** 工作负荷来管理书籍。 管理书籍的过程与管理应用的过程相同。
必须上载 Apple 批量采购计划令牌才能执行上述操作。 目前，只能将书籍分配为**必需的**安装。
在向设备分配一本书时，该设备必须安装内置的 iBooks 应用， 否则最终用户必须重新安装该应用才能阅读书籍。 当前不能使用 Intune 来还原已删除的内置应用。


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>管理批量采购的适用于 iOS 设备的应用程序
通过 [Apple Volume Purchase Program 企业版](http://www.apple.com/business/vpp/)或 [Apple Volume Purchase Program 教育版](http://volume.itunes.apple.com/us/store)购买多个 iOS 应用许可证。 这涉及到从 Apple 网站设置一个 Apple VPP 帐户并将 Apple VPP 令牌上载到 Intune。  然后你可以将你的批量购买信息与 Intune 同步并追踪你的批量购买的应用的使用情况。

## <a name="before-you-start"></a>开始之前
在开始之前，你需要从 Apple 中获取 VPP 令牌并将其上载到 Intune 帐户。 此外，你应了解以下内容：

* 可以将多个批量购买计划令牌与你的 Intune 帐户关联。
* 如果你以前使用过不同产品的 VPP 令牌，必须生成一个新的令牌在 Intune 中使用。
* 每个令牌的有效期为一年。
* 默认情况下，Intune 与 Apple VPP 服务一天同步两次。 可以随时开始手动同步。
* 将 VPP 令牌导入 Intune 之后，不要将同一令牌导入任何其他设备管理解决方案。 这样做可能导致许可证分配和用户记录丢失。
* 在开始将 iOS VPP 与 Intune 配合使用之前，先删除使用其他移动设备管理 (MDM) 供应商创建的任何现有 VPP 用户帐户。 作为安全措施，Intune 不会将那些用户帐户同步到 Intune 中。 Intune 将仅同步 Apple VPP 服务中由 Intune 创建的数据。
* Intune 支持最多添加 256 个 VPP 令牌。

## <a name="to-get-and-upload-an-apple-vpp-token"></a>获取并上传 Apple VPP 令牌

1. 登录到 Azure 门户中。
2. 选择“更多服务” > “其他” > “Intune”。
3. 在“Intune”边栏选项卡上，选择“移动应用”。
1.  在“移动应用”工作负载中，依次选择“设置” > “iOS VPP 标记”。
2.  在 VPP 标记列表边栏选项卡上，单击“添加”。
3.  在“新 VPP 令牌”边栏选项卡中，指定下列信息：
    - **VPP 令牌文件** - 如果尚未注册，则请注册 Volume Purchase Program 企业版或 Volume Purchase Program 教育版。 注册后，为你的帐户下载 Apple VPP 令牌，并在此处选择它。
    - **Apple ID** - 输入与批量购买计划关联的帐户的 Apple ID。
    - **VPP 帐户类型** - 从“企业版”或“教育版”中进行选择。
4. 完成后，请单击“上传”。

该令牌将显示在令牌列表边栏选项卡中。


你可以随时通过选择“立即同步”将 Apple 保存的数据与 Intune 同步。

## <a name="to-assign-a-volume-purchased-app"></a>如何分配批量购买应用

1. 在“移动应用”工作负载中，依次选择“管理” > “获得许可的应用”。
2. 在应用列表边栏选项卡上，选择要分配的应用，然后依次选择“...” >“分配组”。
3. 在<应用名称> -“已分配的组”边栏选项卡中，选择“管理” > “已分配的组”。
4. 选择“分配组”，然后在“选择组”边栏选项卡上，选择要将应用分配到的 Azure AD 用户或设备组。
必须选择**必需**的分配操作。 此外，对设备组的分配可用于 2017 年 1 月之后创建的新租户。 如果你的租户在此之前创建的，并且没有选择将 VPP 应用分配给设备组，请联系 Intune 支持。
5. 完成后，选择“保存”。

有关帮助监视应用分配的信息，请参阅[如何监视应用](apps-monitor.md)。

## <a name="further-information"></a>更多信息

在将应用分配为**必需**安装后，安装该应用的每个用户都将使用许可证。

若要回收许可证，必须将分配操作更改为“卸载”。 卸载应用后，将回收许可证。

具有符合条件的设备的用户首次尝试安装 VPP 应用时，系统将要求其加入 Apple Volume Purchase Program。 继续安装应用前，他们必须执行此操作。

在将 VPP 应用分配为可用后，会直接从应用商店分配应用内容和许可证。

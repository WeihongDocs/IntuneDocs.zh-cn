---
title: "iOS 应用保护策略设置"
titleSuffix: Intune Azure preview
description: "Intune Azure 预览版：本主题介绍适用于 iOS 设备的应用保护策略设置。"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f8b08f2-504c-4b38-bea2-b8a4ef0526b8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: a391f9e16faf315c5fb88191f3de3f8f2f3d5178
ms.lasthandoff: 02/18/2017


---

#  <a name="ios-app-protection-policy-settings"></a>iOS 应用保护策略设置
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

可以在 Azure 门户的“设置”边栏选项卡上为应用保护策略[配置](app-protection-policies.md)本主题所述的策略设置。

有两种类别的策略设置：数据重定位设置和访问设置。 在本主题中，术语***策略托管应用***指使用应用保护策略配置的应用。

##  <a name="data-relocation-settings"></a>数据重定位设置

| Setting | 如何使用 | 默认值 |
|------|------|------|
| **阻止 iTunes 和 iCloud 备份** | 选择“是”，阻止此应用将工作或学校的数据备份到 iTunes 和 iCloud。 选择“否”允许此应用程序将工作或学校的数据备份到 iTunes 和 iCloud。| 是 |
| **允许应用向其他应用传送数据** | 指定哪些应用可从此应用接收数据： <ul><li> **策略托管应用**：仅允许传输到其他策略托管应用。</li> <li>**所有应用**：允许传输到任何应用。 </li> <li>**无**：不允许将数据传输到任何应用，包括其他策略托管应用。</li></ul> 此外，如果将此选项设置为“策略托管应用”或“无”，则将阻止允许 Spotlight Search 在应用内搜索数据的 iOS 9 功能。 <br><br> 有一些豁免应用和服务，Intune 可能会允许向其传输数据。 有关应用和服务的完整列表，请参阅[数据传输豁免](#Data-transfer-exemptions)。 | 所有应用 |
| **允许应用从其他应用接收数据** | 指定哪些应用可将数据传输到此应用： <ul><li>**策略托管应用**：仅允许从其他策略托管应用传输。</li><li>**所有应用**：允许从任何应用传输数据。</li><li>**无**：不允许从任何应用传输数据，包括其他策略托管应用。 </li></ul> <p>  有一些豁免应用和服务，Intune 可能会允许从其传输数据。 有关应用和服务的完整列表，请参阅[数据传输豁免](#Data-transfer-exemptions)。 | 所有应用 |
| **阻止“另存为”** | 选择“是”，在此应用中禁用“另存为”选项。 如果你希望允许使用“另存为”，请选择“否”。 | 否 |
| **限制剪切、复制和粘贴到其他应用程序** | 指定剪切、复制和粘贴操作何时可用于此应用。 选择： <ul><li>**阻止**：不允许在此应用和任何其他应用间进行剪切、复制和粘贴操作。</li><li>**策略托管应用**：允许在此应用和其他策略托管应用间进行剪切、复制和粘贴操作。</li><li>**带粘贴的策略托管应用**：允许在此应用和其他策略托管应用间进行剪切或复制。 允许将任何应用中的数据粘贴到此应用。</li><li>**任何应用**：不限制从此应用和对此应用进行剪切、复制和粘贴。 | 任何应用 |
|**限制显示在 Managed Browser 内的 Web 内容** | 选择“是”，强制在 Managed Browser 应用中打开应用中的 Web 链接。 <br><br> 对于未在 Intune 中注册的设备，策略托管应用中的 Web 链接将仅可在 Managed Browser 应用中打开。 <br><br> 如果正使用 Intune 管理设备，请参阅[使用 Microsoft Intune 的托管浏览器策略管理 Internet 访问](https://docs.microsoft.com/en-us/intune/deploy-use/manage-internet-access-using-managed-browser-policies)。 | 否 |
| **加密应用数据** | 对于策略托管应用，使用 iOS 提供的设备级别的加密方案对数据进行静态加密。 需要 PIN 时，根据应用保护策略中的设置对数据进行加密。 <br><br> 转到[此处](https://support.apple.com/HT202739)官方 Apple 文档，查看哪些 iOS 加密模块由 FIPS 140-2 认证或挂起 FIPS 140-2 证书。 <br><br> 指定何时加密应用中工作或学校数据。 选择： <ul><li>**锁定设备时**：锁定设备时，加密与此策略关联的所有应用数据。</li><li>**锁定设备并具有打开的文件时**：锁定设备时，对与此策略相关联的所有应用数据进行加密，当前已在应用中打开的文件中的数据除外。</li><li>**设备重启后**：设备重启后，对与此策略相关联的所有应用数据进行加密，直到首次解锁设备。</li><li>**使用设备设置**：基于设备上的默认设置对应用数据进行加密。 启用此设置时，用户必须设置并使用 PIN 才能访问其设备。  如果未为设备访问设置 PIN，则不启动应用，并将通过“公司要求先启用设备 PIN 才能访问此应用”消息提示用户设置 PIN。 </li></ul> | 当设备锁定 |
| **禁用联系人同步** | 选择“是”，阻止应用将数据保存到设备上的本机“联系人”应用。 如果选择“否”，应用可将数据保存到设备上的本机“联系人”应用。 <br><br>执行选择性擦除从应用删除工作或学校数据时，将删除从应用直接同步到本机“联系人”应用的联系人。 无法擦除从本机通讯簿同步到另一个外部源中的任何联系人。 目前仅适用于 Microsoft Outlook 应用。 | 否 |
| **禁用打印** | 选择“是”，阻止应用打印工作或学校数据。 | 否 |


> [!NOTE]
> 无数据重定位设置控制 iOS 设备上由 Apple 托管的打开方式功能。 要使用管理 Apple 打开方式，请参阅[使用 Microsoft Intune 管理 iOS 应用之间的数据传输](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)。

## <a name="data-transfer-exemptions"></a>数据传输豁免

有一些豁免应用和平台服务，Intune 应用保护策略可能会允许在某些情况下向其或从其传输数据。 此列表可能会更改以反映有利于安全工作效率的服务和应用。

| 应用/服务名称 | 描述 |
| ---- | --- |
|tel; telprompt | 本机电话应用 |
| Skype | Skype |
| app-settings | 设备设置 |
| itms; itmss; itms-apps; itms-appss; itms-services | App Store |
| calshow | 本机日历 |


## <a name="access-settings"></a>访问设置

| Setting | 如何使用 | 默认值 |
|------|------|------|
| **需要 PIN 才能进行访问** | 选择“是”，需要 PIN 才可使用此应用。 用户首次在工作或学校环境中运行应用时，将提示其设置此 PIN。 默认值 = **是**。<br><br> 为 PIN 强度配置以下设置： <ul><li>**PIN 重置前的尝试次数**：指定用户重置其 PIN 码前必须成功完成输入的尝试次数。 默认值 = **5**。</li><li> **允许简单 PIN**：选择“是”，允许用户使用简单的 PIN 序列，如 1234 或 1111。 选择“否”，阻止用户使用简单的序列。 默认值 = **是**。 </li><li> **PIN 长度**：指定 PIN 序列必须包含的最小位数。 默认值 = **4**。 </li><li> **允许指纹而非 PIN (iOS 8.0+)**：选择“是”，允许用户使用 [Touch ID](https://support.apple.com/en-us/HT201371) 而非 PIN 进行应用访问。 默认值 = **是**。</li></ul> 在 iOS 设备上，可让用户使用 [Touch ID](https://support.apple.com/en-us/HT201371) 而非 PIN 来证明其身份。 用户尝试通过其工作或学校帐户使用此应用时，会提示他们提供其指纹标识而不是输入 PIN。 </li></ul>| 需要 PIN：是 <br><br> PIN 重置尝试次数：5 <br><br> 允许使用简单 PIN：是 <br><br> PIN 长度：4 <br><br> 允许使用指纹：是 |
| **访问需要公司凭据** | 选择“是”，要求用户使用其工作或学校帐户（而不是输入 PIN）登录进行应用访问。 如果将其设置为“是”，则此设置将替代 PIN 或 Touch ID 的要求。  | 否 |
| **阻止在已越狱或取得 root 权限的设备上运行托管应用** |  选择“是”，阻止在已越狱或取得 root 权限的设备上运行此应用。 用户仍能够将此应用用于个人任务，但必须使用其他设备访问此应用中的工作或学校数据。 | 是 |
| **在一定时间后重新检查访问要求（分钟）** | 配置下列设置： <ul><li>**超时**：指定重新检查应用访问要求之前的时间（以分钟为单位）。 默认值 = **30** 分钟。</li><li>**脱机宽限期**：如果设备脱机，请指定重新检查应用访问要求之前的时间（以分钟为单位）。 默认值 = **720** 分钟（12 小时）。</li></ul>| 超时：30 <br><br> 脱机：720 |
| **擦除应用数据前的脱机时间间隔(天)** | 如果设备已脱机超过一段时间，可擦除此应用中的工作或学校数据。 可指定从设备删除工作或学校数据前该设备可脱机的天数。 <br><br> | 90 天 |

##  <a name="add-ins-for-outlook-app"></a>Outlook 应用的加载项

Outlook 最近为 Outlook for iOS 引入了加载项，让你可将热门应用集成到电子邮件客户端中。 Outlook 的加载项可在 Web、Windows、Mac 和 Outlook for iOS 上使用。 由于加载项是通过 Microsoft Exchange 管理的，所以用户能够在 Outlook 和非托管加载项应用程序之间共享数据和邮件，除非用户的 Exchange 关闭了加载项。

如果要阻止最终用户访问和安装 Outlook 加载项（这会影响所有 Outlook 客户端），请确保在 Exchange 管理中心中对角色进行以下更改：

- 若要防止用户安装 Office 应用商店加载项，请从中删除“我的应用商店”角色。
- 若要防止用户侧向加载加载项，请从中删除“我的自定义应用”角色。
- 若要防止用户安装所有加载项，请从中删除“我的自定义应用”和“我的应用商店”角色。

这些说明适用于跨 Web、Windows、Mac 和移动版 Outlook 的 Office 365、Exchange 2016、Exchange 2013。

- 详细了解 [Outlook 的加载项](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx)。
- 详细了解[如何指定可安装和管理 Outlook 应用的加载项的管理员和用户](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx)。

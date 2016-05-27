---
# required metadata

title: Microsoft Intune 中的 Mac OS X 策略设置 |Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune 中的 Mac OS X 配置策略设置

## 常规配置策略设置

使用 Microsoft Intune 的“Mac OS X 常规配置策略”为以下对象配置设置：

-   “设备安全设置”– 从预定义设置列表中进行选择，此列表让你可以控制设备上的一系列功能。

-   “相容和不相容应用”- 指定在你的公司中相容或不相容的应用列表。 “不相容应用报告”可用于查看你在列表中指定的应用对于用户已安装的应用的相容性（但不能实际阻止应用的安装）。

如果此列表中未显示你正在寻找的设置，你可能能够使用 Mac OS X 自定义策略创建它，该策略让你能够使用“Apple 配置器工具”导入所创建的设置。 有关详细信息，请稍后参阅本主题中的“自定义策略设置”。

### 密码设置

|设置名|详细信息|
|----------------|---------------|
|**需要密码才能解锁设备**|指定用户是否必须使用密码才可访问其 Mac 计算机。 **重要提示：**与 iOS 设备不同，在 Mac OS X 设备上，不会立即通知用户更新其密码来符合此设置。|
|**所需的密码类型**|指定所用密码是否可以仅由数值组成，还是必须为“字母数字”  （包含字母和数字）。 **重要提示：**仅在 Mac OS X 10.10.3 及更高版本上支持此设置。|
|**密码中所需的复杂字符数**|指定密码中所需的复杂字符数（0  -  4）。).<br /><br />复杂字符是一个符号，如 ?。'|
|**最短密码长度**|指定密码的最短长度（“4”  到“14”  个字符之间）。|
|**允许简单密码**|允许使用简单密码，如“0000”或“1234”'.|
|**需要提供密码之前处于非活动状态的分钟数**|指定在需要密码来进行解锁之前，计算机必须保持非活动状态的时间。|
|**密码过期(天)**|指定用户在多少天之后必须更改密码（1  -  255 天）。|
|**记住密码历史记录**|此设置用于防止用户使用以前用过的密码。 设置该选项时，还可以设置“防止重用以前的密码”以指定以前使用的不能重复使用的密码数（1  -  24）).|
|**屏幕保护程序激活前处于非活动状态的分钟数**|指定屏幕保护程序激活前计算机必须处于空闲状态的时间。|

### 相容和不相容应用的设置
在“Mac OS X 的相容&amp;不相容应用列表”中，启用“设备的托管设置”，然后使用以下信息指定相容或不相容应用的列表：

> [!NOTE]
> 单个策略只能包含一个相容应用列表或一个不相容应用列表。 不能在同一策略中同时指定两个列表。
> 
> Intune 允许你报告安装了不相容应用的设备。 它不会阻止安装，也不会删除不相容应用。

|设置名|详细信息|
|----------------|---------------|
|**用户安装列出的应用时报告不相容情况**|列出不允许用户安装的 Mac OS X 应用。 如果用户安装任何这些应用，“不相容应用报告”中将报告安装的应用。.|
|**用户安装未列出的应用时不报告不相容情况**|列出允许用户安装的 Mac OS X 应用。 如果用户安装任何其他应用，“不相容应用报告”中将报告安装的应用。.|
|**添加**|将应用添加到选定的列表。 指定你选择的名称（可为应用发布者）和应用的捆绑 ID。 **提示：**若要查找应用的捆绑 ID，请在已安装此应用的 Mac 计算机上执行以下步骤：<ol><li>打开安装应用的文件夹（例如，**/Applications**）)</li><li>选择 &lt;应用名称&gt;.app 捆绑包，然后选择“显示包内容”</li><li>打开“Info.plist”  文件</li><li>检查与“” </li></ol>捆绑 ID 的格式为“com.contoso.appname” |
|**导入应用**|导入你已在逗号分隔值文件中指定的应用列表。 在文件中使用格式、应用名称、发布者和应用捆绑 ID。|
|**编辑**|允许你编辑所选应用的名称、发布者和捆绑 ID。|
|**删除**|从列表中删除选定的应用。|
> [!TIP]
> 有关 Intune 报告的详细信息，请参阅 [Understand Microsoft Intune operations by using reports（通过使用报告了解 Microsoft Intune 操作）](understand-microsoft-intune-operations-by-using-reports.md)。.

> [!IMPORTANT]
> Mac OS X 设备处于休眠模式时，无法传递策略和配置文件或列出它们的清单。 因此，Intune 控制台可能会暂时显示状态“策略设置错误”，直到下一次从休眠模式中唤醒设备。

### 监视相容和不相容应用
使用“不相容应用报告”  查看指定应用的相容性。

#### 运行报表

1.  在 [Microsoft Intune 管理控制台](https://manage.microsoft.com)中，单击“报告” &gt; “不相容应用报告”.

2.  选择你想要检查的设备组，是要检查相容应用还是不相容应用，或是同时检查两者，然后单击“查看报告”.

## Microsoft Intune 中的 Mac OS X 自定义策略设置
使用 Microsoft Intune 的“Mac OS X 自定义配置策略”，将用“Apple Configurator 工具”[](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)创建的设置部署到 Mac OS X 设备。 使用此工具可以创建控制这些设备的操作的许多设置，并将其导出到配置的配置文件中。 然后可将此配置文件导入到 Intune Mac OS X 自定义策略，并向组织中的用户和设备部署这些设置。

此功能旨在使你能够部署不能与 Intune Mac OS X 常规配置策略一起配置的 Mac OS X 设置。

### 先决条件
在开始之前，必须已安装了 Apple Configurator 并创建了包含需部署到用户或设备的设置的配置文件。 可从 [Mac 应用商店](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)下载和了解 Apple Configurator

> [!NOTE]
> Intune 不会报告 Mac OS X 自定义策略中各个设置的合规性。 但会报告策略的总体合规性。

### 常规设置

|设置名|详细信息|
    |----------------|--------------------|
    |**Name**|输入 Mac OS X 自定义策略的唯一名称，以帮助你在 Intune 控制台中识别它。|
    |**说明**|提供对 Mac OS X 自定义策略的概述以及可帮助你查找它的其他相关信息。|


### 自定义设置

|设置名|详细信息|
    |----------------|--------------------|
    |**自定义配置的配置文件名称（对用户显示）**|提供策略的名称，该名称将显示在设备上以及 Intune 策略报告中。|
    |**配置的配置文件**|单击 **“导入”**，然后浏览到使用 Apple Configurator 创建的配置的配置文件。 **提示：**请参阅本主题中的[如何创建配置文件](#BKMK_Prof)以帮助创建配置文件。|
    |**配置的配置文件详细信息**|显示导入的配置的配置文件的 xml 代码。|



### 如何创建配置文件
可以通过以下两种方法创建自定义策略使用的配置文件：

-   从 Apple Configurator 工具中导出文件（扩展名为 **.mobileconfig**）。

-   使用 [Apple 配置文件关键参考](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html)中的合适架构自行创建文件。.


> [!IMPORTANT]
> Mac OS X 设备处于休眠模式时，无法传递策略和配置文件或列出它们的清单。 因此，Intune 控制台可能会暂时显示状态“策略设置错误”，直到下一次从休眠模式中唤醒设备。

### 另请参阅
[使用 Microsoft Intune 策略管理设备上的设置和功能](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


---
title: "Windows Phone 8.1 策略设置 | Microsoft Docs"
description: "Intune 提供了一系列可在 Windows Phone 8.1 设备上进行配置的内置常规设置。 此外，还可指定 OMA-URI 值创建 Intune 未提供的自定义设置。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2fd7ebc53c3b033982297dbce4a091cd9336fbb1


---

# <a name="windows-phone-81-policy-settings-in-microsoft-intune"></a>Microsoft Intune 中的 Windows Phone 8.1 策略设置

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune 提供了一系列可在 Windows Phone 8.1 设备上进行配置的内置常规设置。 此外，还可指定开放移动联盟统一资源标识符 (OMA-URI) 值创建 Intune 未提供的自定义设置。

## <a name="general-configuration-settings"></a>常规配置设置

使用 Microsoft Intune **Windows Phone 常规配置策略（Windows Phone 8.1 及更高版本）**为 Windows Phone 8.1 设备配置以下设置：

-   **“移动设备安全设置”** – 从让你能够控制设备上的一系列功能的预定义设置列表中选择。

-   **符合和不符合要求的应用**- 指定在你的公司中符合和不符合要求的应用列表。 Windows Phone 设备可以阻止或允许这些应用的安装。

### <a name="applicability-settings"></a>适用性设置

|设置名|详细信息|
|----------------|----------------------------------|
|**将所有配置应用到 Windows 10**|此策略中的设置除了可以应用到 Windows Phone 8.1 设备外，还可以应用到 Windows 10 移动设备。|

### <a name="password-settings"></a>密码设置

|设置名|详细信息|
|----------------|------|
|**需要密码才可解锁移动设备**|指定用户是否必须输入密码来访问其设备。|
|**所需的密码类型**|指定需要的密码类型，例如仅限字母数字或数字。|
|**必填密码类型 – 字符集最小数量**|指定密码中必须包括多少个不同的字符集。 有以下四个字符集：小写字母、大写字母、数字和符号。 但是，对于 iOS 设备，此设置指定密码中必须包括的符号的数量。|
|**最短密码长度**|指定密码中所需的最少字符数。|
|**允许简单密码**|指定可使用如“0000”和“1234”等简单密码。|
|**擦除设备前允许的重复登录失败次数**|指定擦除设备前，可输入错误密码的次数。|
|**屏幕关闭前处于不活动状态的分钟数**|指定自动锁定屏幕之前，设备必须保持空闲的时间量。|
|**密码过期（天数）**|指定必须更改设备密码前的天数。|是|是|
|**记住密码历史记录**|指定是否要记住以前用过的密码以防止用户再次使用它们。|
|**“记住密码历史记录”** – **“防止重用以前的密码”**|指定要记住的以前用过的密码的数量。|

### <a name="encryption-settings"></a>加密设置

|设置名|详细信息|
|----------------|------|
|**需要对移动设备加密**|需要对支持的移动设备上的数据进行加密。|

### <a name="system-settings"></a>系统设置

|设置名|详细信息|
|----------------|-----|
|**允许屏幕捕获**|让用户以图像文件形式捕获屏幕内容。|
|**允许提交诊断数据**|允许设备将诊断信息提交到 Microsoft。|

### <a name="cloud-settings--accounts-and-synchronization"></a>云设置 – 帐户和同步

|设置名|详细信息|
|----------------|------|
|**支持 Microsoft 帐户**|允许将 Microsoft 帐户链接至设备。|

### <a name="email-settings"></a>电子邮件设置

|设置名|详细信息|
|----------------|-----|
|**允许自定义电子邮件帐户**|允许设备连接到非 Microsoft 电子邮件帐户。|

### <a name="application-settings---browser"></a>应用设置 - 浏览器

|设置名|详细信息|
|----------------|-----|
|**允许 Web 浏览器**|允许或阻止设备上的内置 Web 浏览器。|

### <a name="application-settings---apps"></a>应用设置 - 应用程序

|设置名|详细信息|
|----------------|-----|
|**允许应用程序商店**|允许用户从设备连接到应用商店。|

### <a name="device-capabilities-settings---hardware"></a>设备性能设置 - 硬件

|设置名|详细信息|
|----------------|-----|
|**允许照相机**|允许或阻止设备的照相机。|
|**允许可移动存储**|允许设备使用可移动存储，如 SD 卡。|
|**允许 Wi-Fi**|启用或禁用设备的 Wi-Fi 功能。|
|**允许 Wi-Fi tethering**|允许在设备上使用 Wi-Fi Tethering。|
|**允许自动连接到免费 Wi-Fi 热点**|允许设备自动连接到免费的 Wi-Fi 热点并自动接受任何使用条款。|
|**允许 Wi-Fi 热点报告**|发送有关 Wi-Fi 连接的信息，以帮助用户发现附近的连接。|
|**允许地理位置**|允许设备利用位置信息。|
|**允许 NFC**|允许使用近场通信的操作。|
|**允许蓝牙**|启用或禁用设备的蓝牙功能。|

### <a name="device-capabilities-settings---features"></a>设备性能设置 - 功能

|设置名|详细信息|
|----------------|----|
|**允许复制和粘贴**|允许在设备上使用复制和粘贴功能。|

### <a name="settings-for-allowed-and-blocked-apps"></a>允许和阻止的应用的设置
在“允许和阻止的应用”列表中，使用以下信息指定想要允许或阻止的应用的列表：

> [!NOTE]
> 单个策略只能包含允许或阻止的应用的列表。 不能在同一策略中同时指定两个列表。

|设置名|详细信息|
|----------------|--------------------|
|**阻止设备打开列出的应用**|列出未由 Intune 托管且不允许用户安装和运行的应用。|
|**仅允许设备安装列出的应用**|列出允许用户安装的应用。 用户无法安装任何其他应用。 自动允许由 Intune 托管的应用。|
|**添加**|将应用添加到选定的列表。 指定你选择的名称、应用商店中应用的 URL 以及应用发布者（可选）。 若要获取更多帮助，请参阅本主题后面的“如何指定应用商店的 URL”。
|**导入应用**|导入你已在逗号分隔值文件中指定的应用列表。 在文件中使用格式、应用程序名称、发布者和应用 URL。|
|**编辑**|允许你编辑选定应用的名称、发布者和 URL。|
|**删除**|从列表中删除选定的应用。|
> [!IMPORTANT]
> 如果为 Windows Phone 8.1 设备指定了允许的应用列表，则必须将公司门户应用添加到此列表中，否则此列表将被阻止。


### <a name="reference-information-for-allowed-and-blocked-apps"></a>有关允许和阻止的应用的参考信息

#### <a name="how-to-specify-urls-to-app-stores"></a>如何指定应用商店的 URL
若要在允许和阻止的的应用列表中指定应用 URL，请使用以下格式：

在 [Windows Phone 应用 + 游戏](http://www.windowsphone.com/en-us/store/overview)页面中，搜索想要使用的应用。

打开应用页面，并将该 URL 复制到剪贴板。 你现在可以在允许的或阻止的应用列表中将它用作 URL。

**例如：** 在应用商店中搜索 Skype 应用。 你将使用的 URL 是 **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**。

## <a name="custom-policy-settings"></a>自定义策略设置
使用 Microsoft Intune **Windows Phone 自定义配置策略**来部署可用于控制 **Windows Phone 8.1 设备**上的功能的 OMA-URI 设置。 这些设置是许多移动设备制造商用来控制设备功能的标准设置。

此功能使你能够部署不能与 Intune 常规配置策略一起配置的 Windows Phone 设置。 若要了解可与这些策略一起配置的设置，请参阅[使用 Microsoft Intune 策略管理设备上的设置和功能](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)。

有关创建 Windows Phone 设备的 OMA-URI 设置的帮助，请参阅 [Windows Phone 8.1 MDM 协议文档](http://technet.microsoft.com/library/dn499787.aspx)。

### <a name="general-settings"></a>常规设置

|设置名|详细信息|
|----------------|--------------------|
|**Name**|输入策略的唯一名称，以帮助你在 Intune 控制台中识别它。|
|**描述**|提供对策略的说明以及可帮助你查找策略的其他相关信息。|

### <a name="oma-uri-settings"></a>OMA-URI 设置

在“OMA-URI 设置”部分，单击“添加”以添加设置。 也可编辑或删除现有设置。

在“添加或编辑 OMA-URI 设置”对话框中，指定以下信息：

|设置名|详细信息|
    |--------|--------------------|
    |**设置名称**|输入 OMA-URI 设置的唯一名称，以帮助你在设置列表中识别它。|
    |**设置描述**|提供对设置进行概述的说明以及帮助你找到该设置的其他相关信息。|
    |**数据类型**|选择将在其中指定此 OMA-URI 设置的日期类型。 选择：<br /><br />-   **字符串**<br />-   **字符串 (XML)**<br />-   **日期和时间**<br />-   **整数**<br />-   **浮点**<br />-   **布尔值**|
    |**OMA-URI（区分大小写）**|指定需为其提供设置的 OMA-URI。|
    |**值**|指定要与之前指定的 OMA-URI 关联的值。|

### <a name="see-also"></a>另请参阅
[使用 Microsoft Intune 策略管理设备上的设置和功能](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO2-->


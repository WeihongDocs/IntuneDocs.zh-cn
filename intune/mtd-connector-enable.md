---
title: "通过 Intune 启用移动威胁防御连接器"
titleSuffix: Intune on Azure
description: "在 Intune 中启用移动威胁防御连接器。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a5dfef35c9f2d2fa543d8b19c2566b25d47b8f72
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2017
---
# <a name="enable-mobile-threat-defense-in-intune"></a>在 Intune 中启用移动威胁防御

> [!NOTE] 
> 本主题适用于所有移动威胁防御合作伙伴。

若要在 Intune 中启用移动威胁防御 (MTD) 连接，应已在 MTD 解决方案控制台中配置了 Intune 连接器。

## <a name="to-enable-the-mtd-connector"></a>启用 MTD 连接器

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用 Intune 凭据登录。 成功登录后，会看到“Azure 仪表板”。

2. 在“Azure 仪表板”中，从左侧菜单中选择“更多服务”，然后在文本框筛选器中键入 Intune。

3. 选择“Intune”，随即显示“Intune 仪表板”。

4. 在“Intune 仪表板”中，选择“设备符合性”，然后选择“设置”部分下的“移动威胁防御”。

5. 在“移动威胁防御”边栏选项卡上选择“添加”。

6. 从下拉列表中选择 MTD 解决方案作为“要设置的移动威胁防御连接器”。

    ![Intune Azure 门户中的 MTD 设置](./media/enable-mtd-connector-1.png)

7. 根据你组织的要求启用切换选项。

## <a name="mtd-toggle-options"></a>MTD 切换选项

根据组织要求，可以决定需要启用哪些 MTD 切换选项。 下面是更多详细信息：

- **将 Android 4.1+ 设备连接到 [MTD 合作伙伴名称] for Work MTD**：如果启用此选项，可以让 Android 4.1 + 设备将安全风险报回 Intune。
    - **如果未收到任何数据则标记为不合规**：如果 Intune 未从 MTD 合作伙伴收到有关此平台上的设备的数据，则将设备视为不合规。
<br></br>
- **将 iOS 8.0+ 设备连接到 [MTD 合作伙伴名称] for Work MTD**：如果启用此选项，可以让 Android 4.1 + 设备将安全风险报回 Intune。
    - **如果未收到任何数据则标记为不合规**：如果 Intune 未从 MTD 合作伙伴收到有关此平台上的设备的数据，则将设备视为不合规。
<br></br>
- **阻止不受支持的操作系统版本**：如果设备运行的操作系统版本低于支持的最低版本，则阻止该版本。

- **合作伙伴无响应之前的天数**：在 Intune 由于连接断开将技术合作伙伴视为无响应之前的天数。 Intune 将忽略无响应 MTD 合作伙伴的符合性状态。

> [!IMPORTANT] 
> 在创建设备符合性和条件性访问策略规则之前，必须先添加和分配 MTD 应用。 这样可以确保最终用户能够安装 MTD 应用，以便访问电子邮件或其他公司资源。

> [!TIP]
> 你可以从“移动威胁防御”边栏选项卡看到 Intune 和 MTD 合作伙伴之间的“连接状态”和“上次同步”时间。

## <a name="next-steps"></a>后续步骤

[使用 Intune 创建移动威胁防御设备符合性策略](mtd-device-compliance-policy-create.md)
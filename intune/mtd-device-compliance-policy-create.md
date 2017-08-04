---
title: "使用 Intune 创建移动威胁防御设备符合性策略"
titleSuffix: Intune on Azure
description: "在 Intune 中创建移动威胁防御设备符合性策略"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6b05522c7390acb3974e088ecd60d13db46ef5a
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2017
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>使用 Intune 创建移动威胁防御 (MTD) 设备符合性策略

> [!NOTE] 
> 本主题适用于所有移动威胁防御合作伙伴。

搭载 MTD 的 Intune 可帮助检测移动设备上存在的威胁和评估相关风险。 可创建评估风险的 Intune 设备符合性策略规则，确定设备是否合规。 然后可使用条件性访问策略，根据设备合规性阻止对服务的访问。

## <a name="before-you-begin"></a>在开始之前

作为 MTD 设置过程的一部分，需在 MTD 合作伙伴控制台中创建一个将各种威胁分类为高、中和低的策略。 现在需要在 Intune 设备符合性策略中设置移动威胁防御级别。

MTD 设备符合性策略先决条件：

-   使用 Intune 设置 MTD 集成

-   在 Intune 中启用 MTD 连接器。

## <a name="to-create-a-mtd-device-compliance-policy"></a>创建 MTD 设备符合性策略

1.  转到 [Azure 门户](https://portal.azure.com/)，然后使用 Intune 凭据登录。

2.  在“Azure 仪表板”中，从左侧菜单中选择“更多服务”，然后在文本框筛选器中键入 Intune。

3.  选择“Intune”，随即显示“Intune 仪表板”。

4. 在“Intune 仪表板”中，选择“设备符合性”，然后选择“管理”部分下的“策略”。

5.  选择“创建策略”，输入设备符合性“名称”、“说明”，选择“平台”，然后选择“设置”部分下的“配置”。

6.  在“符合性策略”边栏选项卡上选择“设备运行状况”。

7.  在“设备运行状况”边栏选项卡上，从“要求设备不高于移动威胁防御级别”下的下拉列表中选择移动威胁级别。

    a.  **安全**：这是最安全的选项。 设备不能存在任何威胁，且仍可访问公司资源。 如果发现了任何威胁，设备都将被视为不合规。

    b。  **低**：如果设备上仅存在低级威胁，则该设备为合规。 低级以上的任意威胁都将使设备不合规。

    c.  **中**：如果设备上发现的威胁为低级别或中等级别，设备为合规。 如果设备中检测到高级威胁，则视为不合格。

    d.  **高**：这是最不安全的选项。 此选项将许可所有威胁级别，且仅将移动威胁防御用作报告目的。 设备必须使用此设置激活 MTD 应用。

8.  单击“确定”两次，然后选择“创建”。

> [!IMPORTANT]
> 如果为 Office 365 或其他服务创建条件性访问策略，将考虑上述合设备符合性评估，阻止不合规的设备访问公司资源，直到解决威胁。

## <a name="to-assign-a-mtd-device-compliance-policy"></a>分配 MTD 设备符合性策略

若要为用户分配设备合规性策略，请选择之前已配置的策略。 可在“设备符合性策略”边栏选项卡中找到现有策略。

1. 选择要分配给用户的策略，然后选择“分配”。 此操作将打开边栏选项卡，可以在其中选择“Azure Active Directory 安全组”并将其分配给策略。

2. 选择“选择组”以打开显示 Azure AD 安全组的边栏选项卡。  选择“选择”会将策略部署到用户。

    > [!NOTE] 
    > 你已将策略应用于用户。 将评估策略针对的用户所使用设备的合规性。
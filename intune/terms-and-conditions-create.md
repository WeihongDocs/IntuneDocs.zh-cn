---
title: "设置 Microsoft Intune 中的条款和条件"
titleSuffix: Intune Azure preview
description: "设置用户将在公司门户中看到的 Intune 条款和条件。 "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d53e91e24988d1bc71ff8df425f0d82e0fc43b58
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---

# <a name="ensure-users-accept-company-terms-for-access"></a>确保用户接受公司的访问条款

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

作为 Intune 管理员，可以选择要求用户先接受公司的条款和条件，然后他们才可以使用“公司门户”注册其设备并访问公司资源，例如应用和电子邮件。 条款和条件配置是可选的。

可以创建多个条款集并将其分配给不同的组，以便支持不同的语言。

## <a name="create-terms-and-conditions"></a>创建条款和条件
完成这些步骤来创建条款和条件。 显示名称和描述供管理使用，条款属性将向“公司门户”中的用户显示。

1. 在 Azure 门户中，选择“更多服务” > “监视 + 管理” > “Intune”。

2. 在 Intune 边栏选项卡上，选择“设备注册”，然后选择“条款和条件”。

3. 选择“创建”。
![显示条款和条件“创建”按钮的 Intune 门户的屏幕截图](media/terms-create-terms.png)

4. 在展开的边栏选项卡中，指定下列信息：

   - **显示名称**：Intune 门户中的条款名称。 用户看不到此名称。

   - **描述**：帮助在 Intune 门户中标识此条款集的可选详细信息。

5. 选择“定义使用条款”旁边的箭头打开“条款和条件”边栏选项卡，然后输入以下信息：

   ![显示最终用户接受条款和条件屏幕以及条款摘要的屏幕截图](./media/terms-summary-create.png)

   - **标题**：用户在公司门户中看到的标题。

   - **条款摘要**：阐释用户接受条款的含义的文字。 例如，“注册设备即表示同意 Contoso 制定的使用条款。 继续操作前，请仔细阅读条款。”

   - **条款和条件**：用户可查看且必须接受或拒绝的条款和条件。

6. 选择“确定”，然后选择“创建”。

## <a name="assign-terms-and-conditions"></a>分配条款和条件

可以将条款和条件分配给用户组，这些用户必须先接受它们，然后才能使用“公司门户”。

1. 在 Azure 门户中，选择“更多服务” > “监视 + 管理” > “Intune”。

2. 在 Intune 边栏选项卡上，选择“设备注册”，然后选择“条款和条件”。

3. 在条款和条件列表中，选择想要分配的条款，然后选择“已分配组”。
![Intune 门户显示条款和条件分配的“选择组”按钮和“选择”按钮的“分配组”边栏选项卡屏幕快照](media/terms-assign-groups.png)

4. 单击“选择组”按钮并在“选择组”边栏选项卡中选择想要向其分配条款的组，然后单击“选择”。

5. 在“已分配组”边栏选项卡中，单击“保存”。  现已将条款和条件分配给所选组中的用户。 在用户下一次访问公司门户时将提示他们接受条款。

   ![显示最终用户接受条款和条件屏幕以及条款摘要的屏幕截图](./media/terms-summary-accept.png)

## <a name="monitor-a-terms-and-conditions"></a>监视条款和条件

1. 在 Azure 门户中，选择“更多服务” > “监视 + 管理” > “Intune”。 在 Intune 边栏选项卡上，选择“设备注册”，然后选择“条款和条件”。
2. 在条款和条件列表中，选择想要查看其接受状态的条款，然后选择“接受状态”。

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>使用多个版本的条款和条件
可以编辑条款和条件并管理其版本。 建议增加版本号，并在条款和条件发生重大变更时要求用户接受。 如果修改错别字或更改格式设置，则维持当前版本号。

1. 在 Azure 门户中，选择“更多服务” > “监视 + 管理” > “Intune”。

2. 在 Intune 边栏选项卡上，依次选择“设备注册”、“条款和条件”，选择想要修改的条款和条件，然后选择“属性”。

4. 在“属性”边栏选项卡上，选择“条款和条件”，然后根据需要修改“标题”、“条款摘要”和“条款和条件”。 如果作出的更改需要用户重新接受新的条款，则单击“要求用户重新接受，并将版本号递增为”

4.  选择“确定”，然后选择“保存”。

---
title: "添加用户并授予权限"
description: "将本地用户与 Azure AD 同步，并授予对 Intune 订阅的管理员权限"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4289fdbdadbef34f06514b62722f84354534ae65
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2017
---
# <a name="add-users-and-give-administrative-permission-to-intune"></a>添加用户并授予对 Intune 的管理权限

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

本主题指导管理员如何向 Intune 添加用户以及 Intune 服务中可用的管理权限。

作为管理员，可直接添加用户或从本地 Active Directory 同步用户。 添加后，用户可注册设备并访问公司资源。 还可为用户提供更多权限，包括“全局管理员”和“服务管理员”权限。

## <a name="add-users-to-intune"></a>添加用户到 Intune
可通过 [Office 365 门户](https://www.office.com/signin)或 [Azure Intune 门户](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)手动将用户添加到 Intune 订阅。 管理员可以通过编辑用户帐户来分配 Intune 许可证。 可通过 Office 365 门户或 Intune Azure 门户分配许可证。 若要深入了解如何使用 Office 365 门户，请参阅[向 Office 365 门户逐一或批量添加用户](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。

### <a name="add-intune-users-in-the-office-365-admin-center"></a>在 Office 365 管理中心添加 Intune 用户
1. 登录到 [Office 365 门户](https://www.office.com/signin)。
2. 在 Office 365 菜单中，选择“管理员”。
3. 在管理中心，选择“添加用户”。

  ![Office 365 管理员屏幕截图](media/office-add-user.png)

4. 指定下列用户详细信息：
  - 名
  - 姓
  - 显示名称 - 在 Intune 门户中显示
  - 用户名 - Intune 门户中的 UPN 名称
  - **位置**
  - 联系人信息（可选）
  - 密码 - 自动生成或指定

     ![Office 365 管理员屏幕截图](media/office-add-user-details.png)

5. 分配 Intune 许可证。 选择“产品许可证”，然后选择所需的产品许可证。
6. 选择“添加”创建新用户。

### <a name="add-intune-users-in-the-azure-intune-portal"></a>在 Azure Intune 门户添加 Intune 用户
1. 登录到 [Azure 门户](https://portal.azure.com)。 转到“监视和管理” > “Intune”。 还可为 Intune 搜索资源。
2. 选择“用户”。
3. 在管理中心，选择“添加用户”。
  ![Office 365 管理员屏幕截图](media/intune-add-user.png)
4. 指定下列用户详细信息：
  - **Name**
  - 用户名 - Azure Active Directory 门户中的新名称 ![Office 365 管理员屏幕截图](media/intune-add-user-info.png)选择“确定”以继续。
5. 或者，也可以指定下列用户属性：
  - 个人资料 - 包括“职务”和“部门”在内的工作信息
  -  组 - 选择要为用户添加的组
  - 目录角色 - 授予用户 Intune 的管理权限

  选择“创建”，将新用户添加到 Intune。
6. 选择“个人资料”，然后为新用户选择“使用位置”。 只有指定使用位置后，才能为新用户分配 Intune 许可证。 选择“保存”以继续。
    ![Office 365 管理员屏幕截图](media/intune-add-user-loc.png)
7. 依次选择“许可证”和“分配”，为此用户分配 Intune 许可证。 只有获得 Intune 许可证后，才能注册设备或访问公司资源。 依次选择“产品”、“许可证类型”、“选择”和“分配”。

## <a name="grant-admin-permissions"></a>授予管理员权限

在 Intune 订阅中添加用户后，最好为一些用户授予管理员权限：
-   [全局管理员](#tenant-administrator)：使用 Office 365 门户分配此类型的管理员。 全局管理员可管理订阅，包括帐单、云存储以及管理有权使用 Intune 的用户。
-   [自定义或受限管理员](#service-administrator)：使用 Office 365 或 Azure Intune 控制台分配此类型的管理员来完成日常任务，包括设备和计算机管理、部署策略和应用，以及运行报表。

![Office 365 门户分配角色图像。](./media/office-assign-roles.png)

### <a name="types-of-administrators"></a>管理员类型

为用户分配一个或多个管理员权限。 这些权限定义了各用户的管理范围及其能够管理的任务。 尽管部分服务可能不支持某些权限，但管理员权限在不同的 Microsoft 云服务之间是通用的。 Intune 使用以下管理员权限：

- 全局管理员 -（Office 365 和 Intune）访问 Intune 中的所有管理功能。 默认注册 Intune 的人员为全局管理员。 全局管理员是唯一可分配其他管理员角色的管理员。 在组织中可有多个全局管理员。 建议最好只向公司中的少数人分配此角色，以降低业务风险。
- 帐务管理员 -（Office 365 和 Intune）采购、管理订阅、管理支持票证并监视服务运行状况。
- 密码管理员 -（Office 365 和 Intune）重置密码、管理服务请求并监视服务运行状况。 密码管理员仅限为用户重置密码。
- 服务管理员 -（Office 365）打开 Microsoft 支持请求，并查看服务仪表板和消息中心。 除打开支持票证并读取外，他们还具有“仅查看”权限。
- 用户管理管理员 -（Office 365 和 Intune）重置密码、监视服务运行状况、添加和删除用户帐户以及管理服务请求。 用户管理管理员不能删除全局管理员、创建其他管理员角色，或为其他管理员重置密码。

默认情况下，用于创建 Microsoft Intune 订阅的帐户是全局管理员。 最佳做法是，不要将全局管理员用于日常管理任务。 管理员不需要 Intune 的许可证即可访问 Intune 管理员控制台。 有关详细信息，请参阅 [What is an Azure AD directory?](http://technet.microsoft.com/library/jj573650.aspx)（什么是 Azure AD 目录？）中的 Azure AD 租户部分。

若要访问 Office 365 门户，必须将帐户设置为“允许登录”。 在 Intune 门户中的“配置文件”下，将“阻止登录”设置为“否”以允许访问。 此状态与拥有订阅许可证不同。 默认情况下，所有用户帐户均为“已允许”。 无管理员权限的用户可使用 Office 365 门户重置 Intune 密码。

## <a name="sync-active-directory-and-add-users-to-intune"></a>同步 Active Directory 并将用户添加到 Intune
可配置目录同步，将用户帐户从本地 Active Directory 导入到包含 Intune 用户的 Microsoft Azure Active Directory (Azure AD)。 让本地 Active Directory 服务与你所有基于 Azure Active Directory 的服务相连接，使管理用户标识变得更简单。 还可以配置单一登录功能，使用户的身份验证体验熟悉且简单。 通过将同一 [Azure AD 租户](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)与多个服务相链接，先前同步的用户帐户便可用于所有基于云的服务。

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>如何使用 Azure AD 同步本地用户
使用 Azure AD 同步本地用户所需的唯一工具是 [Azure AD Connect 向导](https://www.microsoft.com/download/details.aspx?id=47594)。 Azure AD Connect 向导为将你的本地身份基础结构连接到云提供简化的指导式体验。  选择拓扑和需求（单个目录或多个目录、密码同步或联合身份验证）。 向导将部署和配置所有必需组件，以使连接正常运行。 其中包括：同步服务、Active Directory 联合身份验证服务 (AD FS) 和 Azure AD PowerShell 模块。

> [!TIP]
> Azure AD 连接包含之前作为目录同步和 Azure AD Sync 发布的功能。 了解有关[目录集成](http://technet.microsoft.com/library/jj573653.aspx)的详细信息。 若要了解如何将用户帐户从本地目录同步到 Azure AD，请参阅 [Active Directory 与 Azure AD 之间的相似之处](http://technet.microsoft.com/library/dn518177.aspx)。
---
title: "Intune 数据仓库 API 终结点 | Microsoft Docs"
description: "参考主题介绍 API URL 结构。"
keywords: "Intune 数据仓库"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7723bb42eedcd97142f039ca52b60911fa91838b
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2017
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune 数据仓库 API 终结点

可将 Intune 数据仓库 API 与具有基于特定角色的访问控制和 Azure AD 凭据的帐户配合使用。 然后，使用 OAuth 2.0 向 REST 客户端授予 Azure AD 权限。 最后会形成一个有意义的可调用数据仓库资源的 URL。

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD 和 Intune 凭据要求

身份验证和授权基于 Azure AD 凭据和 Intune 基于角色的访问控制 (RBAC)。 默认情况下，租户的所有全局管理员和 Intune 服务管理员都可访问该 API。 使用 Intune 角色为更多用户分配访问“报告资源”的权限，让更多用户拥有访问权限。

访问 API 的要求如下：

  -  必须向用户分配 Intune 许可证
  -  用户必须是以下任一身份：
      -  Azure AD 全局管理员
      -  Intune 服务管理员
      -  对“报告”资源具有基于角色的访问权限的用户

## <a name="authorization"></a>授权

Azure Active Directory (Azure AD) 使用 OAuth 2.0 使你能够在你的  Azure  AD  租户中授予对  Web  应用程序和  Web  API  的访问权限。 本指南介绍如何在不使用开源库的情况下发送和接收 HTTP 消息（无语言限制）。 OAuth 2.0 规范的[第 4.1 节](https://tools.ietf.org/html/rfc6749#section-4.1)介绍了 OAuth 2.0 授权代码流。

有关详细信息，请参阅[授权使用 OAuth 2.0 和 Azure Active Directory 访问 Web 应用程序](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)。

## <a name="api-url-structure"></a>API URL 结构

数据仓库 API 终结点读取每个集的实体。 API 支持 **GET** HTTP 谓词和查询选项的子集。

Intune 的 URL 使用以下格式：  
https://fef.{***location***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***entity-collection***}?api-version={***api-version***}

该 URL 包含以下元素：

| 元素 | 示例 | 描述 |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| 位置 | msua06 | 可通过查看 Azure 门户中的数据仓库 API 边栏选项卡获取基 URL。 |
| 实体集合 | 日期 | OData 实体集合的名称。 有关数据模型中集合和实体的详细信息，请参阅[数据模型](reports-ref-data-model.md)。 |
| api-version | beta | 版本是指要访问的 API 版本。 有关详细信息，请参阅[版本](#API-version-information)。 |


## <a name="api-version-information"></a>API 版本信息

此 API 的当前版本为：`beta`。 

## <a name="odata-query-options"></a>OData 查询选项

当前版本支持以下 OData 查询参数：`$skip, $top, $filter, $orderby`。
---
title: "用户 | Microsoft Docs"
description: "Intune 数据仓库 API 中实体集合的“用户”类别的参考主题。"
keywords: "Intune 数据仓库"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b9739299c52c668117116f54c08715f1218d130
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-user-entity"></a>用户实体引用

“用户”类别包含用户实体，用于定义数据模型中的用户和代理属性。

**User**

用户实体列出了企业中分配有许可证的所有 Azure Active Directory (Azure AD) 用户。

| 属性  | 说明 | 示例 |
|---------|------------|--------|
| UserKey |数据仓库中用户的唯一标识符 - 代理键 |123 |
| UserId |用户的唯一标识符 - 类似于 UserKey，但该标识符是自然键 |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |用户的电子邮件地址 |John@constoso.com |
| DisplayName |用户的显示名称 |John |
| IntuneLicensed |指定此用户是否获得 Intune 许可。 |True/False |
| IsDeleted |表明是否已更新此用户记录。  True - 此用户拥有新纪录，其中含有此表中的更新的字段。 False - 此用户的最新记录。 |True/False |
| StartDateInclusiveUTC |在数据仓库中创建此用户的 UTC 日期和时间 |2016/11/23 - 中午 12:00:00 |
| EndDateExclusiveUTC |IsDeleted 更改为 True 时的 UTC 日期和时间 |2016/11/23 - 中午 12:00:00 |
| IsCurrent |表明此用户记录目前是否在数据仓库中 |True/False |
| RowLastModifiedDateTimeUTC |上次在数据仓库中修改此用户的 UTC 日期和时间 |2016/11/23 - 中午 12:00:00 |

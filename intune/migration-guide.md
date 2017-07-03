---
title: "Intune 移动设备管理迁移指南"
description: "本指南可引导客户逐步了解从第三方 MDM 提供程序迁移到 Microsoft Intune 所涉及的各种详细信息。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 1911c8a2460a98218027c40a26d81f1ca4c482f5
ms.openlocfilehash: 9e86f342413a0f31c51d7a56f862986c433309eb
ms.contentlocale: zh-cn
ms.lasthandoff: 06/13/2017


---

# <a name="intune-migration-guide"></a>Intune 迁移指南

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

![Intune MDM 迁移指南图解](./media/MDM-migration-guide-art.PNG)

要成功迁移到 Intune，要从制定一个坚实可行的计划开始，充分考虑当前移动设备管理 (MDM) 环境、业务目标和技术要求等因素。 此外，还需要具有关键的利益相关者，他们将支持并协同完成迁移计划。

本指南可引导你逐步了解从第三方 MDM 提供程序迁移到 Intune 所涉及的各种详细信息。

## <a name="whats-included-in-this-guide"></a>该指南包括什么？

本指南包含两个阶段，这两个阶段均包含任务、策略和战略指导，用于帮助你逐步完成迁移到 Intune MDM 的完整过程。

-   [阶段 1：为移动设备管理准备 Intune] (migration-guide-prepare.md)

    -   [评估 MDM 迁移要求](migration-guide-prepare.md#assess-mdm-requirements)

    -   [基本设置](migration-guide-setup.md)

    -   [配置设备和应用管理策略](migration-guide-configure-policies.md)

    -   [配置应用保护策略] (migration-guide-app-protection-policies.md)

    -   [特殊迁移注意事项](migration-guide-considerations.md)

-   [阶段 2：迁移活动](migration-guide-campaign.md)

    -   [通信计划](migration-guide-communication-plan.md)

    -   [推动最终用户采用条件访问](migration-guide-drive-adoption.md)
    
    -   [典型迁移周期](migration-guide-cycle.md)
        -   [监视迁移](migration-guide-cycle.md#monitoring-migration)
        -   [迁移后](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>假设

-   你已经在概念验证 (PoC) 环境中评估了 Intune，并已决定将其用作组织中的 MDM 解决方案。

-   现在，你已对 Intune 及其功能有了一定的了解。 

> [!NOTE]
> 如果想要在迁移前更深入了解 Intune，请查看 [Intune 评估指南](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune)。

## <a name="before-you-begin"></a>在开始之前

请注意，你的新的 Intune 部署可能不同于旧的 MDM 部署。 与传统的 MDM 服务不同，Intune 重点关注标识驱动访问控制，因此不需要使用网络代理设备来控制组织网络外围之外的移动设备对公司数据的访问。 Microsoft 提供了解决方案，通过一系列紧密集成的云服务（统称为企业客户端 + 安全产品/服务）来确保云本身数据服务的安全。

-   查看 [Intune 的常见使用方式](migration-guide-prepare.md#assess-mdm-requirements)。

## <a name="next-steps"></a>后续步骤

[阶段 1：为移动设备管理准备 Intune] (migration-guide-prepare.md)

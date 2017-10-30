---
title: "使用 Windows AutoPilot Deployment 计划注册 Windows 设备"
description: "了解如何使用 Windows AutoPilot Deployment 计划注册新的 Windows 10 设备。"
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: 76b709f97b349966fbca7115959f64a56741380b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2017
---
# <a name="enroll-windows-devices-using-windows-autopilot-deployment-program"></a>使用 Windows AutoPilot Deployment 计划注册 Windows 设备
Windows AutoPilot Deployment 计划简化了设备预配。 当前，生成和维护自定义操作系统映像耗时过久。 在将其提供给最终用户之前，可能需要花费大量时间将自定义操作系统映像应用到新设备上。 使用 Microsoft Intune 和 AutoPilot 就可向最终用户提供全新设备，而无需生成、维护自定义操作系统映像以及将其应用到设备。 当使用 Intune 来管理 AutoPilot 设备时，可在注册之后对策略、配置文件和应用等进行管理。 有关优势、方案和先决条件的概述，请参阅 [Overview of Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot)（Windows AutoPilot 概述）。

## <a name="prerequisites"></a>先决条件
- [必须向组织注册设备](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot#registering-devices-to-your-organization)
- [已启用的 Windows 自动注册](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium 订阅](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)<!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="synchronize-devices"></a>同步设备
将已注册设备同步到 Intune，以便对其进行配置。

1. 登录到 [Azure](https://portal.azure.com/)。
2. 选择“更多服务” > “监视 + 管理” > “Intune”。
3. 在“Intune”边栏选项卡上，选择“设备注册”。
4. 在“Windows 注册”边栏选项卡的“Windows AutoPilot 部署计划”部分中，选择“设备”。
5. 单击“同步”以导入注册的设备。 将显示一条指示同步正在进行中的消息。
6. 刷新视图以查看新设备。 此过程可能耗时数分钟才能完成，具体取决于正在同步的设备数目。  

## <a name="create-an-autopilot-deployment-profile"></a>创建 AutoPilot 部署配置文件
AutoPilot 部署配置文件用于配置 AutoPilot设备。
1. 登录到 [Azure](https://portal.azure.com/)。 
2. 选择“更多服务” > “监视 + 管理” > “Intune”。
3. 在“Intune”边栏选项卡上，选择“设备注册”。
4. 在“Windows 注册”边栏选项卡的“Windows AutoPilot 部署计划”部分中，选择“部署配置文件”。
5. 单击“创建配置文件”，然后选择名称和可选说明。 
6. 对于“联接类型”，请选择“已联接 Azure AD”。
7. 对于“全新体验 (OOBE)”，请配置下列选项，然后单击“确定”： 
   - **隐私设置**：选择是否向用户显示隐私设置。 
   - **最终用户许可协议 (EULA)**：选择是否向用户显示 EULA。
   - **用户帐户类型**：选择用户的帐户类型是“管理员”还是“标准”用户。
8. 单击“创建”以创建配置文件。 AutoPilot 部署配置文件现在即可分配给设备。
     
   > [!Note]    
   > 使用全部 AutoPilot 部署配置文件来配置以下设置：
   > - 跳过 Cortana、OneDrive 和 OEM 注册设置页
   > - 为工作或学校帐户自动设置
   > - 公司或学校品牌的登录体验    

## <a name="assign-an-autopilot-deployment-profile"></a>分配 AutoPilot 部署配置文件
在创建 AutoPilot 部署配置文件后，可将其分配给所选设备。

1. 登录到 [Azure](https://portal.azure.com/)。 
2. 选择“更多服务” > “监视 + 管理” > “Intune”。
3. 在“Intune”边栏选项卡上，选择“设备注册”。
4. 在“Windows 注册”边栏选项卡的“Windows AutoPilot 部署计划”部分中，选择“设备”。
5. 选择要向其分配部署配置文件的设备。 可以在“状态”列中进行筛选以轻松查找设备，而无需分配的配置文件。 
6. 单击“分配配置文件”，选择“AutoPilot 部署配置文件”，然后单击“分配”。 将显示一条指示分配正在进行中的消息。
7. 刷新视图以查看已分配给设备的配置文件。 此过程可能耗时数分钟才能完成，具体取决于所选设备的数目。 

> [!Note]
> 新配置文件将分配到设备。 但是，需在设备重置并重新注册之后，配置文件才可应用于已在 Intune 中注册的设备。

### <a name="assign-a-different-autopilot-deployment-profile"></a>分配不同的 AutoPilot 部署配置文件
在将某个 AutoPilot 部署配置文件分配给设备后，如果要分配不同的配置文件，请将新配置文件分配给设备。  

## <a name="edit-an-autopilot-deployment-profile"></a>编辑 AutoPilot 部署配置文件 
在成功创建 AutoPilot 部署配置文件后，可对该部署配置文件的某些部分进行编辑。   
1. 登录到 [Azure](https://portal.azure.com/)。 
2. 选择“更多服务” > “监视 + 管理” > “Intune”。
3. 在“Intune”边栏选项卡上，选择“设备注册”。
4. 在“Windows 注册”边栏选项卡的“Windows AutoPilot 部署计划”部分中，选择“部署配置文件”。 
5. 选择要编辑的配置文件。 
6. 单击左侧的“属性”以更改该部署配置文件的名称或说明。 更改后请单击“保存”。 
7. 单击“设置”以对 OOBE 设置进行更改。 更改后请单击“保存”。 

> [!NOTE]
> 更新后的配置文件将分配到设备。 但是，需在设备重置并重新注册之后，已更新的配置文件才可应用于已在 Intune 中注册的设备。 

## <a name="using-autopilot-in-other-portals"></a>在其他门户中使用 AutoPilot
如果无意使用移动设备管理，还可以使用其他门户，例如在适用于企业的 Microsoft 应用商店中使用 AutoPilot。 尽管使用其他门户也是一种选择，但我们建议仅使用 Intune 来管理 AutoPilot 部署。 如果同时使用 Intune 和其他门户，则 Intune 将无法：
- 显示对在 Intune 中创建、但在其他门户中编辑的配置文件的更改
- 同步在其他门户中创建的配置文件
- 显示对在其他门户中完成的配置文件分配的更改
- 同步在其他门户中完成的配置文件分配

## <a name="next-steps"></a>后续步骤
在为已注册的 Windows 10 设备配置 Windows AutoPilot 后，了解如何管理这些设备。 有关详细信息，请参阅[什么是 Microsoft Intune 设备管理？](https://docs.microsoft.com/intune/device-management)
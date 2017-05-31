---
title: "创建 Intune 设备配置文件 | Intune Azure 预览版"
titleSuffix: Intune Azure preview
description: "Intune Azure 预览版：了解如何创建 Intune 设备配置描述文件。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a719b3f53076a55f1e888a9ddf8e98c7074dd25f
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>如何在 Microsoft Intune 中创建设备配置文件

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


1. 登录到 Azure 门户中。
2. 选择“更多服务” > “监视 + 管理” > “Intune”。
3. 在“Intune”边栏选项卡上，选择“配置设备”。
2. 在“设备配置”边栏选项卡上，选择“管理” > “配置文件”。
2. 在显示配置文件列表的边栏选项卡上，选择“创建配置文件”。
3. 在“创建配置文件”边栏选项卡上，指定下列信息：
    - **名称** - 输入新配置文件的描述性名称。
    - **说明** - 输入配置文件的可选说明。
    - **平台** - 选择要创建的配置文件的平台类型。
    - **配置文件类型** - 选择要创建的配置文件的类型。 可用类型的列表根据你选择的平台而有所不同。
    - **设置** - 有关每种配置文件类型的设置的信息，请参阅以下主题：
        -  [设备功能设置](device-features-configure.md)
        -  [设备限制设置](device-restrictions-configure.md)
        -  [电子邮件设置](email-settings-configure.md)
        -  [VPN 设置](vpn-settings-configure.md)
        -  [Wi-Fi 设置](wi-fi-settings-configure.md)
        -  [Windows 10 版本升级设置](edition-upgrade-configure-windows-10.md)
        -  [证书设置](certificates-configure.md)
        -  [Windows 信息保护设置](windows-information-protection-configure.md)
        -  [教育设置](education-settings-configure.md)
        -  [自定义设置](custom-settings-configure.md)

    ![创建设备配置文件](./media/create-device-profile.png)
4. 完成配置设置后，在“创建配置文件”边栏选项卡上，选择“创建”。

将创建配置文件并在“配置文件列表”边栏选项卡上显示。
如果想要继续操作并将此配置文件分配到组，请参阅[如何分配设备配置文件](device-profile-assign.md)。


### <a name="next-steps"></a>后续步骤
有关如何分配设备配置文件的信息，请参阅[如何使用 Microsoft Intune 分配设备配置文件](device-profile-assign.md)。

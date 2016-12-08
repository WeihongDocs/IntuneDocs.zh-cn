---
title: "结合使用应用和 MAM CA | Microsoft Intune"
description: "了解 MAM CA 如何帮助控制有权访问 O365 服务的应用的概念。"
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: df77e1473532399056c3e0c1b4c4db3c7b6ba995
ms.openlocfilehash: 0fc24f1c93cfcdb86c2a66c9a027b4ed9c516dab


---
# <a name="what-to-expect-when-using-an-app-with-mam-ca"></a>将应用与 MAM CA 结合使用时的预期行为
MAM CA 会借助必须在设备上存在的代理应用来验证已批准的应用程序的标识：
*  在 **iOS** 上，**Azure Authenticator 应用**是代理应用。
* 在 **Android** 上，**Intune 公司门户应用**是代理应用。 

系统会提示首次登录 MAM CA 支持的应用（如 OneDrive 或 Outlook）的最终用户安装代理应用并向 Azure AD 注册设备。 Azure AD 中的设备注册（以前称为工作区加入）会创建针对其颁发令牌的设备记录和证书。  这与 **MDM 注册****不**同。 不会应用管理配置文件或应用，并且设备上没有应用的清单。  安装代理应用并注册设备的过程只在首次使用托管应用时进行。

下面是直接派生自该设备的属性列表：

* alternativeSecurityIds（Azure Active Directory 证书指纹和公钥哈希）
* deviceOSType
* deviceOSVersion
* displayName

## <a name="to-remove-a-device-from-azure-ad-registration"></a>从 Azure AD 注册删除设备。
可通过 Azure AD 管理控制台删除设备注册，IT 管理员通常采用此种方式。  还可由最终用户在设备本身完成删除操作。

* **Azure AD 管理员控制台**：在 Azure AD 管理控制台中**，删除想要删除的设备。
* **iOS 设备**：打开 Azure Authenticator 应用，轻扫帐户左侧，然后选择注销。  
* **Android 设备**：卸载公司门户应用或从“系统设置”删除帐户。



## <a name="mam-ca-with-conditional-access-based-on-device-compliance"></a>MAM CA 与基于设备合规性的条件访问  

可以在 [Intune 管理员控制台](https://manage.microsoft.com)或 [Azure AD Premium 管理控制台] (https://manage.windowsazure.com) 上配置[基于设备合规性的条件访问](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)（**设备 CA**）。 设备 CA 要求用户只能通过符合 Intune 设备合规性策略的 Intune 托管设备或已加入域的电脑连接到 Exchange Online。  如果用户属于针对 MAM CA 和设备 CA 策略的一个或多个安全组，则用户必须满足以下两个要求之一：
* 用于访问服务的应用是 MAM CA 支持的移动应用，并且运行该应用的设备安装了 **iOS 身份验证器（适用于 iOS 设备）**或**公司门户应用（适用于 Android 设备）**。
* 用于访问服务的设备是 **Intune 托管并符合** Intune 设备合规性策略，或者是**已加入域的电脑**。  下面是一些示例，可帮助说明这一点：
  * 如果用户尝试从**本机 iOS 电子邮件应用**进行连接，则需要位于**托管且合规的设备**上，因为 MAM CA 不支持本机邮件应用。
  * 如果用户尝试从 **Windows 家庭电脑**进行连接，则**设备 CA 策略**会进行应用，从而要求用户必须使用已加入域的电脑。




## <a name="next-steps"></a>后续步骤
[为 MAM 应用创建 Exchange Online 策略](mam-ca-for-exchange-online.md)

[阻止不具有新式验证的应用](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>另请参阅

[使用 MAM 策略保护应用数据](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Nov16_HO2-->


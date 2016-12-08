---
title: "停用设备 | Microsoft Intune"
description: "Intune 支持选择性擦除和完全擦除，通过删除其策略和公司门户从 Intune 管理中删除该设备。"
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b76e9e16ef1fa6870783326630ae74d07ae59cbb
ms.openlocfilehash: be3a30535fc9cebad5d4a167b75c484ddafd7f85


---

# <a name="retire-devices-from-intune-management"></a>从 Intune 管理停用设备

无论设备是公司拥有的还是个人的，最终都需要从 Intune 管理中删除一个托管设备。 出于多种原因，可能需要停用设备：

-   用户以计划方式离开公司（“托管式”离开）
-   用户突然离开（被解雇、辞职等）。
-   设备丢失
-   改变设备用途（转移给其他用户、重新用于其他目的等）

可以对作为移动设备进行管理的设备执行选择性擦除或完全擦除，或者可以锁定设备并重置密码。 擦除设备可释放用户的订阅，以添加其他设备。 也可以停用使用 Intune 客户端软件管理的电脑。

## <a name="wipe-data-and-apps-from-devices"></a>从设备中擦除数据和应用
选择性擦除和完全擦除都可以通过删除设备的策略和公司门户，将设备从 Intune 管理中删除。 因此，设备不再拥有登录到公司资源（如 Microsoft SharePoint、电子邮件或 Office 365）所必需的凭据。

对于已在 Intune 注册其自有设备的员工而言，[选择性擦除](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe)是首选的操作选项，因为它不会影响设备上的个人信息。 仅删除公司数据。

对于需要重新调整用途的设备，你也可以使用[完全擦除](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe)，这会将设备重置为出厂默认设置。

## <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>在 Azure Active Directory 门户中删除设备

1.  使用组织凭据登录到 [http://aka.ms/accessaad](http://aka.ms/accessaad) 或 [https://portal.office.com](https://portal.office.com)，然后选择“管理中心”&gt;“Azure AD”。

2.  创建 Azure 订阅（如果没有）。 如果拥有付费帐户，则不需要使用信用卡或进行付款。 选择“注册免费的 Azure Active Directory”订阅链接。

4.  选择“Active Directory”，然后选择组织。

5.  选择“用户”选项卡。

6.  选择要删除其设备的用户。

7.  选择**设备**。

8.  选择适当的设备，然后选择“删除设备”。 下一次与 Active Directory 同步时，将删除该设备。 这通常发生在 4 小时内。 同步之后，将从管理中删除该设备。 这会从该用户的设备限制中删除一台设备。

## <a name="retire-managed-computers"></a>停用被管理的计算机
可以从 Intune 管理控制台的管理中删除 Intune 客户端软件管理的计算机。 删除的同时还会卸载客户端软件，并从计算机中删除 Intune 策略。 请参阅有关[停用使用 Intune 客户端软件管理的计算机](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md)的信息。

## <a name="block-access-a-device"></a>阻止访问设备
如果丢失了某个设备，或者因为某位员工离开公司时未归还公司拥有的硬件而必须要停用设备，则还可以[重置密码和远程锁定](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)该设备。 尽管你可能已将设备标记为丢失，但此操作可以防止公司信息被误用。

你还需要从该员工的 Intune 用户帐户吊销许可证。 这将释放许可证，然后可以将该许可证分配给新的用户帐户。

## <a name="retire-hardware"></a>停用硬件
有时，设备本身已达到了其寿命终点。 在这种情况下，使用完全擦除[重置为出厂设置](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)将删除所有的数据并从 Intune 中删除设备。 然后，可以根据公司的策略处理掉硬件。

### <a name="see-also"></a>另请参阅
[使用完全擦除或选择性擦除保护数据](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Nov16_HO3-->


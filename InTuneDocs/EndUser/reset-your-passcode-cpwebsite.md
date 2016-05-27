---
# required metadata

title: 从公司门户网站重置设备密码 | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# 从公司门户网站重置设备密码

如果丢失了设备 PIN 或在 Intune 中注册的设备的密码，则可以使用[公司门户网站](http://portal.manage.microsoft.com)进行重置。 公司门户网站是一个网页，可以用于管理计算机和在 Intune 中注册的设备，还可以在使用公司门户应用时用它来处理你可以执行的大多数相同任务。

> [!NOTE] 可能在公司门户网站上无法看到“重置密码”按钮，这要取决于 IT 管理员配置 Intune 的方式。 Windows 8.1 和 Windows RT 设备不支持密码重置。

重置密码：

1.  打开[公司门户网站](http://portal.manage.microsoft.com)，然后点击要重置其密码的设备。

2.  点击“重置密码”

    ![tap-passcode-to-reset](./media/iwp-1-tap-reset-passcode.png)

3.  点击“注销”，然后使用工作或学校凭据重新登录。 必须在五分钟内重新登录。

    ![sign-out-sign-back-in](./media/iwp-2-sign-out.png)

4.  点击“重置密码”

    ![tap-reset-passcode](./media/iwp-3-tap-reset-passcode-after-signin.png)

    检查此表以了解“重置密码”在设备上的工作方式。

    |平台|Support|
    |------------|-----------|
    |Android|创建新的临时字母数字密码。|
    |iOS|从设备删除密码且不会创建新的临时密码。 如果使用的是 Touch ID，则需要在设备上对其进行重新设置，因为重置密码时会将其删除。|
    |Windows 10（仅适用于移动设备）|创建新的临时字母数字密码。 支持 Windows Hello。|
    |Windows Phone 8.1|创建新的临时数字密码。|
    解锁设备后，可以转到设备上的“设置”来设置新密码。

5.  解锁设备，然后通过转到设备上的“设置”来设置新密码或更改临时密码。

    若要查看确认密码已重置成功的通知，请单击公司门户网站右上角的通知标志。

### 另请参阅
[使用 Intune 公司门户网站](using-the-intune-company-portal-website.md)

<!--HONumber=May16_HO2-->


---
title: "管理设备上的 iOS 激活锁定 | Microsoft Docs"
description: "Microsoft Intune 可以帮助你管理 iOS 激活锁定，它具有 iOS 7.1 和更高版本设备上的“查找我的 iPhone”应用的功能。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d05c9d7a78474c19e142bca94e232289fbfba1d9
ms.openlocfilehash: a6fa910c0a8ec1a9542e03a276dbb8d0757d75b4


---

# <a name="help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune"></a>通过 Microsoft Intune 的绕过激活锁定帮助保护 iOS 设备

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune 可以帮助你管理 iOS 激活锁定，它具有 iOS 8.0 和更高版本设备上的“查找我的 iPhone”应用的功能。 当用户在设备上打开了“查找我的 iPhone”应用时，激活锁定将自动启用。 启用后，任何人都必须先输入用户的 Apple ID 和密码，然后才能执行以下操作： 

-   关闭“查找我的 iPhone”

-   擦除设备

-   重新激活设备

## <a name="how-activation-lock-affects-you"></a>激活锁定对你有何影响
尽管激活锁定可帮助保护 iOS 设备的安全，并可提高找回丢失和被盗设备的几率，但对于 IT 管理员来说，此功能仍然带来了许多挑战。 例如：

-   某个用户在设备上设置了激活锁定。 该用户之后离开了公司并返回使用其设备。 如果不提供用户的 Apple ID 和密码，则不能重新激活该设备。

-   你需要报告启用了激活锁定的所有设备。

-   更新你组织中的设备分配情况时，你希望将某些设备分配重新给另一个部门。 你只能重新分配未启用激活锁定的设备。

为了帮助解决这些问题，Apple 在 iOS 7.1 中引入了绕过激活锁定。 借助此功能，你无需用户的 Apple ID 和密码即可删除监管设备中的激活锁定。 监管设备可以生成设备特定的绕过激活锁定代码，该代码存储在 Apple 的激活服务器上。

> [!TIP]
> 在 iOS 设备的监管模式下，你可以使用 Apple Configurator 来锁定设备，以将设备的功能限制为完成特定的业务目的。 监管模式通常仅适用于公司拥有的设备。

## <a name="how-intune-helps-you-manage-activation-lock"></a>Intune 如何帮助你管理激活锁定
Intune 可以请求运行 iOS 8.0 和更高版本的监管设备的激活锁定状态。 仅就监管设备而言，Intune 可以检索绕过激活锁定代码并直接将代码发布到设备。 如果已擦除设备，可通过使用空的用户名和代码作为密码来直接访问设备。

**此功能的业务优势有**：

-   用户能够获得 Find My iPhone 应用所具有的安全优势。

-   你可以让用户在知道如下事实的情况下进行工作：当需要重新调整设备的用途时，你可以停用或解锁设备。

## <a name="how-to-use-activation-lock-bypass-from-the-intune-admin-console"></a>如何从 Intune 管理员控制台使用绕过激活锁定
> [!IMPORTANT]
> 绕过设备上的激活锁定后，如果“查找我的 iPhone”应用处于打开状态，将自动应用新的激活锁定。 因此，**你应实际拥有该设备，才能执行此过程**。

1.  在 [Microsoft Intune 管理控制台](https://manage.microsoft.com)中，选择**组** &gt; **所有设备** &gt; **公司拥有的所有设备**。

2.  选择想要绕过其“激活锁定”的设备。 选择“绕过激活锁定”。

3.  阅读警告消息。 选择“是”以继续。

你可以在设备的详细信息页上查看解锁请求的状态。

## <a name="how-to-see-which-devices-are-using-activation-lock"></a>如何查看哪些设备正在使用激活锁定
有两种方式可以查看哪些设备正在使用激活锁定：

-   运行“移动设备清单报告” 。 此报告将通过显示“激活锁定状态”和“监管”列来指示设备的状态。 “监管”  的值为“是”  或“否” ，“激活锁定状态”  的值为：

    -   已使用绕过代码启用

    -   未使用绕过代码启用(未监管设备)

    -   未使用旁路代码启用(无法到达设备)

    -   未启用

    对于不运行 iOS 8.0 或更高版本的设备而言，“激活锁定状态”框为空。

-   在组视图中选择一个设备以在“设备详细信息”窗格中查看激活锁定状态。

    如果选择“公司拥有的所有设备”节点中的设备，并为该设备启用了激活锁定，则还可以看到绕过代码。 此代码可用于手动发布绕过激活锁定命令。

    > [!IMPORTANT]
    >Intune 每七天从设备中对激活锁定执行一次清查。 因此，设备可能无法在 Intune 控制台中立即显示其激活锁定状态。


### <a name="see-also"></a>另请参阅
[停用设备](retire-devices-from-microsoft-intune-management.md)
[使用远程锁定和密码重置功能帮助保护设备](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)



<!--HONumber=Jan17_HO4-->


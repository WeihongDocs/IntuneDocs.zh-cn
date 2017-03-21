---
title: "添加 Apple Configurator 序列号"
titleSuffix: Intune Azure preview
description: "Intune Azure 预览版：了解如何使用 Apple Configurator 将序列号添加到公司拥有的 iOS 设备。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 26d253f013195cc18f9a97b8259c603d707d22bf
ms.lasthandoff: 02/18/2017


---

# <a name="add-apple-configurator-serial-numbers"></a>添加 Apple Configurator 序列号

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

若要[使用 Apple Configurator 和设置助理注册公司拥有的 iOS 设备](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)，请使用以下步骤将序列号添加到 Intune。 可以一次添加一个序列号，也可以上传序列号的逗号分隔值 (CSV) 文件。 添加序列号后，即可向其分配配置文件。 配置文件包含要应用于设备的特定管理设置。

[选择在 Intune 中注册 iOS 设备的方式](choose-ios-enrollment-method.md)中介绍了注册 iOS 设备的其他方法。

**将 Apple Configurator 序列号添加到 Intune**

1. 创建没有标题的两列逗号分隔值 (.csv) 列表。 在左列添加 IMEI 标识符，在右列添加详细信息。 目前，该列表的最大长度为 500 行。 在文本编辑器中，该 .csv 列表可能如下所示：

    F7TLWCLBX196,设备详细信息</br>
    DLXQPCWVGHMJ,设备详细信息

2. 在 Azure 门户中，选择“更多服务” > “监视 + 管理” > “Intune”。

3.  在“Intune”边栏选项卡上，选择“注册设备”，然后选择“Apple 注册”。

4. 在“管理 Apple Configurator 注册设置”下，选择“Apple Configurator 序列号”。

5. 在“Apple Configurator 序列号”边栏选项卡上，选择“添加”。

6. 在“添加序列号”边栏选项卡上，选择要应用于导入的序列号的配置文件。 若要导入包含新详细信息（将覆盖现有信息）的文件，请选择“覆盖现有标识符详细信息”以将现有详细信息替换为新的详细信息。

7. 导航到序列号的 .csv 文件，然后选择“添加”。

## <a name="assign-a-profile-to-specific-serial-numbers"></a>将配置文件分配给特定序列号

通过 Intune 可以从 Azure 门户中两个不同位置分配配置文件。 可以使用下面的步骤，也可以在创建配置文件的“Apple Configurator 注册配置文件”边栏选项卡中分配配置文件（请参阅[使用设置助理通过 Apple Configurator 注册 iOS 设备](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)。 只能在已创建配置文件后，才能使用以下步骤分配配置文件。

1. 在 Azure 门户中，选择“更多服务” > “监视 + 管理” > “Intune”。

2. 在“Intune”边栏选项卡上，选择“注册设备”，然后选择“Apple 注册”。

3. 在“Apple Configurator 序列号”边栏选项卡上，选择要向其分配配置文件的序列号，然后选择“分配配置文件”。

4. 在“分配配置文件”边栏选项卡上，选择要分配的配置文件，然后选择“分配”。

## <a name="delete-serial-numbers"></a>删除序列号
可以删除以前导入的序列号。 只能先取消注册设备后，才能删除序列号。 删除序列号后，无法通过设置助理使用 Apple Configurator，除非重新添加序列号。

## <a name="view-the-state-of-a-device"></a>查看设备状态
设备序列号可以具有以下两种状态之一：

- 已注册 - 设备已注册，并已连接到 Intune 服务
- 未连接 - 设备从未连接到 Intune 服务。
- 挂起重置 - 设备已注册，但进行了更改（例如，更改了注册设置或应用的 DEP 配置文件）。 如果更改了设备的 DEP 配置文件，取消注册然后重新注册设备之后，才会应用更改。

**查看序列号状态**

在“Apple Configurator 序列号”边栏选项卡上，选择想查看其状态的序列号，然后在“状态”项中查看。

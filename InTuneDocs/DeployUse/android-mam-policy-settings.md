---
# required metadata

title: Android MAM 策略设置 | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune 中的 Android 移动应用管理策略设置
可以在 Azure 门户的“设置”边栏选项卡上为 MAM 策略[配置](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)下面所述的策略设置。
有两种类别的策略设置，即“数据重定位”和“访问”设置：

##  数据重定位设置
术语**策略托管应用**指使用 MAM 策略配置的应用。
- **阻止 Android 备份：**选择“是”以禁用，或选择“否”以允许备份策略托管应用中的公司数据。

  **默认值 = 是**
- **允许应用将数据传输到其他应用：**选择其中一个选项以指示可接收策略托管应用中的公司数据的应用：
  -   **策略托管应用**：仅允许传输到具有 MAM 策略的应用
  -   **所有应用**：允许传输到任何应用
  -   **无**：不允许将数据传输到任何应用

  **默认值 = 策略托管应用**
- **允许应用从其他应用接收数据：**指定允许将数据传输到策略托管应用的应用：
  -   **策略托管应用**：仅允许从其他策略托管应用传输数据
  -   **所有应用**：允许从任何应用传输数据
  -   **无**：不允许从任何应用传输数据

      **默认值 = 所有应用**

-   **阻止“另存为”：**选择“是”以在任何使用此策略的应用中禁用“另存为”选项。 如果你希望允许使用“另存为”，请选择“否”。

  **默认值 = 是**
- **限制用其他应用剪切、复制和粘贴：**指定何时应限制剪切、复制和粘贴操作。 选择：
  -   **阻止**：不允许在策略托管应用间进行剪切、复制和粘贴操作。
  -   **策略托管应用**：仅允许在策略托管应用间进行剪切、复制和粘贴操作。
  -   **带粘贴的策略托管应用**：允许在策略托管应用间进行剪切或复制。 允许将剪切或复制自任何应用的数据粘贴至此应用。
  -   **任何应用**：不限制在任何应用间进行剪切、复制和粘贴操作。

    **默认值 = 带粘贴的策略托管应用**
-   **将 Web 内容限制为在托管浏览器中显示：**如果启用此设置，应用内的任何链接都将在托管浏览器中打开。

  对于未在 Intune 中注册的设备，策略托管应用中的 Web 链接将仅在使用移动应用管理策略的托管浏览器应用中打开。

  如果你正使用 Intune 管理设备，请参阅 [manage internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies.md)（使用 Microsoft Intune 的托管浏览器策略管理 Internet 访问）

    **默认值 = 是**
- **加密应用数据：**选择“是”以启用加密。 如果启用此设置，与移动应用管理策略关联的应用将由 Microsoft 进行加密。 数据在文件 I/O 操作期间同步加密。 设备存储中的内容始终被加密。

  **默认值 = 是**

- **ContactSyncDisabled：**选择“是”以防止联系人信息同步到设备上的本机通讯簿应用。 如果选择“否”，应用会将联系人信息保存到设备上的本机通讯簿应用中。<br/>如果通过执行选择性擦除来删除公司数据，则将删除从应用直接同步到本机通讯簿的联系人。 无法擦除从本机通讯簿同步到另一个外部源中的任何联系人。 此设置目前仅适用于 **Microsoft Outlook** 应用。

  **默认值 = 是**

##  Android 访问策略设置
术语**策略托管应用**指使用 MAM 策略配置的应用

- **访问需要简单 PIN：**选择“是”以要求使用 PIN 访问策略托管应用。 用户首次在工作环境中运行应用时，将提示其进行此设置。

 **默认值 = 是**
- **PIN 重置之前的尝试次数：**指定输入 PIN 码的尝试次数，达到该次数后用户必须重置 PIN。

 **此设置没有默认值。**
- **访问需要公司凭据：**选择“是”以要求使用公司凭据而不是 PIN 进行应用访问。  如果将其设置为“是”，则此设置将替代 PIN 或 Touch ID 的要求。  将提示用户提供其公司凭据。

  **默认值 = 否**
- **阻止在已越狱或取得 root 权限的设备上运行托管应用：**选择“是”以阻止在已越狱或取得 root 权限的设备上运行应用。 用户仍将能够将这些应用用于个人任务，但必须使用其他设备进行工作。

  **默认值 = 是**
- **以下时间过后重新检查访问要求(分钟)**-   **超时：**重新检查应用访问要求之前的时间（以分钟为单位）。
  -   **脱机宽限期：**如果设备脱机，请指定重新检查应用访问要求之前的时间（以分钟为单位）。

    **默认值 = 30 分钟超时，720 分钟脱机宽限期**

-   **擦除应用数据前的脱机时间间隔(天)：**可以选择在设备脱机一段时间后擦除公司数据。  可以指定从设备删除公司数据前该设备可以脱机的天数。 **提示：**输入值为 0 将关闭此设置。

  **默认值 = 90 天**
- **阻止屏幕捕获和 Android 助手（Android 6 Marshmallow 或更高版本）：**选择“是”，以在使用该应用时阻止设备的屏幕捕获和 **Android 助手**功能。


<!--HONumber=May16_HO2-->


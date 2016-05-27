---
# required metadata

title: 在 Microsoft Intune 控制台中配置和部署移动应用程序管理策略 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configure and deploy mobile application management policies in the Microsoft Intune console
Microsoft Intune 中的移动应用程序管理策略让你可以修改你所部署的应用的功能，以帮助它们符合你的公司合规性和安全策略。 例如，你可以限制在托管的应用内进行剪切、复制和粘贴操作，或配置应用以在托管的浏览器内打开所有 Web 链接。

移动应用管理策略支持：

-   运行 Android 4 和更高版本的设备。

-   运行 iOS 7 和更高版本的设备。

> 移动应用程序管理策略支持向 Intune 注册的设备。
> 
> 如果你正在查找有关如何为不受 Intune 管理的设备创建应用管理策略的信息，请参阅[通过 Microsoft Intune 使用移动应用管理策略保护应用数据](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

与其他 Intune 策略不同，你不会直接部署移动应用程序管理策略。 而是将该策略与你想要进行限制的应用相关联。 当应用部署并安装在设备上时，你指定的设置将起作用。

若要将限制应用到应用，该应用必须包含 Microsoft 应用软件开发工具包 (SDK)。 有两种方式获得此类应用：

-   **使用策略托管应用** – 内置了应用 SDK。 要添加此类型的应用，你可以从 iTunes 应用商店或 Google Play 等应用商店指定应用的链接。 对于此类应用，无需进一步的处理。 请参阅[可配合 Microsoft Intune 移动应用程序管理策略使用的应用](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)的列表

-   “使用‘已包装的’应用”– 使用 **Microsoft Intune 应用包装工具**对应用进行重新封装，以将应用 SDK 包括在内。 该工具通常用于处理公司内部开发的应用。 它可用于处理从应用商店下载的应用。 请参阅[使用 Microsoft Intune 应用包装工具为移动应用程序管理准备 iOS 应用](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)和[使用 Microsoft Intune 应用包装工具为移动应用程序管理准备 Android 应用](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)

某些托管应用（比如用于 iOS 和 Android 的 Outlook 应用）支持**多身份**。 这意味着 Intune 仅对公司帐户或应用程序中的数据应用管理设置。

例如，使用 Outlook 应用：

-   如果用户配置公司和个人电子邮件帐户，则 Intune 仅对公司帐户应用管理设置，并不管理个人帐户。

-   如果设备已停用或已取消注册，则仅从设备中删除公司的 Outlook 数据。

-   使用的公司帐户必须与用于向 Intune 注册设备的帐户相同。

> 如果将 Intune 与 Configuration Manager 结合使用，请参阅[如何使用 Configuration Manager 中的移动应用程序管理策略控制应用](https://technet.microsoft.com/library/mt131414.aspx)

## 创建和部署具有移动应用程序管理策略的应用

-   **步骤 1：** 获取指向策略托管应用的链接，或创建已包装的应用。

-   **步骤 2：** 将应用发布到你的云存储空间。

-   **步骤 3：** 创建移动应用程序管理策略。

-   **步骤 4：** 选择将应用与移动应用程序管理策略相关联的选项，然后部署该应用。

-   **步骤 5：** 监视应用部署。

## **步骤 1：**获取指向策略托管应用的链接，或创建包装的应用

-   **获取策略托管应用的链接** - 从应用商店查找并记录你想要部署的策略托管应用的 URL。

    例如，iPad 适用的 Microsoft Word 的 URL 是 **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**

-   **创建包装的应用** — 使用主题[使用 Microsoft Intune 应用包装工具为移动应用程序管理准备 iOS 应用](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)和[使用 Microsoft Intune 应用包装工具为移动应用程序管理准备 Android 应用](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)中的信息创建包装的应用。

    该工具创建你将应用发布到云存储空间将使用的经过处理的应用。

## **步骤 2：** 将应用发布到你的云存储空间
发布托管的应用时，过程有所差异，具体取决于你发布的是策略托管的应用，还是使用 Microsoft Intune App Wrapping Tool for iOS 进行处理的应用。

#### 若要发布策略托管的应用

1.  当你准备好将应用上载到云存储空间时，请按照[在 Microsoft Intune 中为移动设备添加应用](add-apps-for-mobile-devices-in-microsoft-intune.md)中的说明进行操作

2.  对于 iOS 应用，在“选择如何将此软件提供给设备”下选择“来自应用商店的托管 iOS 应用”

    对于 Android 应用，选择“外部链接”

3.  在 **“指定 URL”**下，输入你之前记录的托管应用的 URL。

上载完成后，你会看到已上载的应用的 **“软件属性”** 页面上的 **“应用管理策略”** 为 **“是”** 。

验证软件上载成功后，继续步骤 3。

#### 要发布使用 Microsoft Intune 应用包装工具处理的应用

1.  当你准备好将应用上载到云存储空间时，请按照[在 Microsoft Intune 中为移动设备添加应用](add-apps-for-mobile-devices-in-microsoft-intune.md)中的说明进行操作

2.  在“选择如何将此软件提供给设备”下选择“软件安装程序”

3.  在“软件安装程序文件类型”下选择“iOS 应用包(&#42;.ipa 文件)”

上载完成后，你会看到已上载的应用的 **“软件属性”** 页面上的 **“应用管理策略”** 为 **“是”** 。

验证软件上载成功后，继续步骤 3。

## **步骤 3：**创建移动应用程序管理策略

1.  在 [Microsoft Intune 管理控制台](https://manage.microsoft.com)中，单击“策略” &gt; “概述” &gt; “添加策略”

2.  配置并部署以下 **“软件”** 策略之一，这取决于你想要为其配置应用的设备类型：

    -   **移动应用程序管理策略 （Android 4 和更高版本）**

    -   **移动应用程序管理策略 （iOS 7 及更高版本）**

    你可以使用建议的设置，或对设置进行自定义。 有关详细信息，请参阅[使用 Microsoft Intune 策略管理设备上的设置和功能](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

3.  根据需要配置下列设置。 该选项可能有所差异，这取决于你配置策略的设备类型。

|设置名|详细信息|
    |---------|--------------------|
    |**Name**|为此策略指定名称。|
    |**描述**|（可选）为此策略指定描述。|
    |**限制显示在企业托管浏览器内的 Web 内容**|如果启用此设备，应用内的任何链接都将在托管浏览器中打开。 你必须部署此应用，此选项才能工作。|
    |**“阻止 Android 备份”** 或 **“阻止 iTunes 和 iCloud 备份”**|禁止从应用备份任何信息。|
    |**允许应用向其他应用传送数据**|指定该应用可以发送数据的应用。 你可以选择不允许将数据传输到任何应用、仅允许传输到其他托管的应用或允许传输到任何应用。 此设置不控制移动设备上的**打开方式**功能的使用。<br /><br />例如，不允许数据传输时，即把数据传输限制为短信发送、分配图片到联系人以及发布到 Facebook 或 Twitter 等服务。<br /><br />对于 iOS 设备，若要防止托管应用和非托管应用之间的文档传输，还必须配置和部署移动设备安全策略，该策略启用设置“允许在其他非托管应用中使用托管文档”。如果你选择仅允许传输到其他托管的应用，则 Intune PDF 和图片查看器（如果已部署）将用于打开各自类型的内容。<br /><br />此外，如果你将此选项设置为“策略托管应用”或“无”，则将阻止允许 Spotlight Search 在应用内搜索数据的 iOS 9 功能。|
    |**允许应用从其他应用接收数据**|指定应用可以接收数据的应用。 你可以选择不允许从任何应用进行数据传输，仅允许从其他托管应用进行传输或允许从任何应用进行传输<br /><br />对于支持多身份的 iOS 应用（其中 Intune 仅将管理设置应用到公司帐户或应用中的数据），以及应用了移动应用程序管理策略的已注册设备，当用户访问不受移动应用程序管理策略管理的应用中的数据时，该数据将被视为公司数据并受到该策略的保护。|
    |**防止“另存为”**|禁止使用 **另存为** 选项，以将数据保存到使用此策略的任意应用中的个人云存储位置（例如 OneDrive - 个人或 Dropbox）。|
    |**限制剪切、复制和粘贴到其他应用程序**|指定应用使用剪切、复制和粘贴操作的方法。 选择：<br /><br />“阻止”– 不允许在本应用和其他应用间进行剪切、复制和粘贴操作。<br /><br />“策略托管的应用”– 仅允许在本应用和其他托管的应用之间进行剪切、复制和粘贴操作。<br /><br />“可粘贴的策略托管应用”– 仅允许将从本应用剪切或复制的数据粘贴到其他托管的应用。 允许将剪切或复制自任何应用的数据粘贴至此应用。<br /><br />“任何应用”– 没有任何剪切、复制和粘贴操作限制。<br /><br />若要在托管的应用之间复制和粘贴数据，那么两个应用必须都配置了“策略托管的应用”或“可粘贴的策略托管应用”设置。|
    |**访问需要简单 PIN**|要求用户输入他们指定使用此应用的 PIN 号码。 将会要求用户在首次运行该应用时进行设置。|
    |**重置 PIN 前的尝试次数**|指定输入 PIN 码的尝试次数，达到该次数后用户必须重置 PIN。|
    |**访问需要公司凭据**|要求用户在访问应用前必须输入他们的公司登录信息。|
    |**访问要求设备符合公司策略**|仅允许设备在未越狱或获取根权限时使用此应用。|
    |**在一定时间后重新检查访问要求（分钟）**|在 **“超时”** 字段，指定应用启动后重新检查访问要求前的时间段。|
    |**离线宽限期**|如果设备离线，指定应用重新检查访问要求前的时间段。|
    |**加密应用数据**|指定与本应用相关的所有数据都将加密，包括外部存储的数据，例如 SD 卡。<br /><br />**适用于 iOS 的加密**<br /><br />对于与 Intune 移动应用程序管理策略关联的应用，使用 OS 提供的设备级加密对静态数据进行加密。 通过必须由 IT 管理员设置的设备 PIN 策略启用。 需要 PIN 时，数据将根据移动应用程序管理策略的设置进行加密。 正如 Apple 文档所述，[iOS 7 所使用的模块经过了 FIPS 140-2 的认证](http://support.apple.com/en-us/HT202739)<br /><br />**适用于 Android 的加官**<br /><br />对于与 Intune 移动应用程序管理策略关联的应用，加密由 Microsoft 提供。 根据移动应用程序管理策略的设置，数据在文件 I/O 运行过程中同步加密。 Android 上托管的应用利用平台加密库使用 CBC 模式的 AES-128 加密。 加密方法没有获得 FIPS 140-2 认证。 设备存储中的内容将始终被加密。|
    |**“阻止屏幕捕捉”** （仅限于 Android 设备）|指定在使用该应用时，阻止设备的屏幕捕捉功能。|

4.  完成后，请单击“保存策略”

新的策略将在“策略”  工作区的“配置策略”  节点处显示。

## **步骤 4：** 将应用与移动应用程序管理策略相关联，然后部署该应用。
部署该应用，确保你选择 **“移动应用管理”** 页面上的移动应用程序管理策略，以关联策略和应用。

有关详细信息，请参阅[在 Microsoft Intune 中部署应用](deploy-apps.md)

> 对于运行 iOS 7.1 之前的操作系统的设备，关联的策略只有在卸载应用后才能删除。
> 
> 如果设备从 Intune 取消注册，策略也不会从应用中删除；任何应用了策略的应用都将保留策略设置，即使卸载应用并重新安装也将如此。

### 应用已部署在设备上时应该如何操作
也存在这样一种情况：当你部署应用时，目标用户或设备之一已经安装了非托管版本的应用，例如用户从应用商店安装了 Microsoft Word。

在这种情况下，必须要求用户手动卸载非托管的版本，才能安装所配置的托管版本。

但是，对于运行 iOS 9 及更高版本的设备，Intune 将自动要求用户提供许可以接管现有应用。 如果用户同意，则应用将由 Intune 管理，并将应用你为其关联的任何移动应用程序管理策略。

> 如果设备处于监督模式，则 Intune 无需要求用户提供许可即可接管现有应用。

## **步骤 5：** 监视应用部署。
创建并部署关联移动应用程序管理策略的应用后，使用以下步骤监视应用并解决任何策略冲突的问题。

#### 若要查看订阅的状态

1.  在 [Microsoft Intune 管理控制台](https://manage.microsoft.com)中，单击“组” &gt; “概述”

2.  执行以下步骤之一：

    -   单击**“所有用户”**，然后双击你想要检查其设备的用户。 在“用户属性”页面，单击“设备”，然后双击你想要检查的设备。

    -   单击“所有设备” &gt; “所有移动设备”。 在“设备组属性”页面，单击“设备”，然后双击你想要检查的设备。

3.  从 **“移动设备属性”** 页面单击 **“策略”** 以查看已部署至设备的移动应用程序管理策略列表。

4.  选择你想要查看的移动应用程序管理策略的状态。 你可以在底部窗格查看策略详细信息，并展开其节点以显示其设置。

5.  在各个移动应用程序管理策略的 **“状态”** 列下，将显示 **“符合”**、 **“符合（待定）”**或 **“错误”** 。 如果所选择的策略有一项或多项冲突设置，将会在该字段中显示 **“错误”** 。

6.  发现了冲突后，你可以将冲突策略设置修改为使用相同设置，或对应用和用户仅部署一个策略。

### 如何解决策略冲突
如果在第一次部署到用户或设备时出现移动应用程序管理策略冲突，则冲突中指定的设置值将从部署到应用的策略中删除，并且应用将使用内置冲突值。

如果在后续部署到应用或用户时出现移动应用管理策略冲突，则冲突的指定设备值将不会更新到部署到应用的移动应用管理策略，并且应用将使用该设置的现有值。

如果设备或用户收到两个冲突策略，则适用以下行为：

-   如果策略已经部署到设备，则现有策略设置不会被覆盖。

-   如果尚无策略部署到设备，并且两个冲突设置已经部署，则将使用设备内的默认设置。





<!--HONumber=May16_HO2-->


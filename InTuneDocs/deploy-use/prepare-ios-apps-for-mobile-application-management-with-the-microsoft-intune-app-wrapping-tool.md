---
title: "使用 Intune 应用包装工具包装 iOS 应用 | Microsoft Intune"
description: "通过本主题中提供的信息了解不更改应用代码本身即可包装 iOS 应用的方法。 准备应用以便应用移动应用管理策略。"
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba4ace8106e83f3579cbaf98dcea8ef240a202a9
ms.openlocfilehash: d150c97197e11d4a81727dca5ddd8eb1310aa193


---

# <a name="prepare-ios-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>使用 Intune 应用包装工具为移动应用程序管理准备 iOS 应用

使用适用于 iOS 的 Microsoft Intune 应用包装工具更改内部 iOS 应用的行为，方法是启用 Intune 应用保护功能，而无需更改应用自身的代码。

该工具是在应用周围创建包装程序的 macOS 命令行应用程序。 处理应用后，可以使用 IT 管理员部署的 Intune [移动应用程序管理策略](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)来更改应用的功能。

若要下载该工具，请参阅 GitHub 上的 [Microsoft Intune App Wrapping Tool for iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios)（适用于 iOS 的 Microsoft Intune 应用包装工具）。



## <a name="fulfill-the-prerequisites-for-the-app-wrapping-tool"></a>满足应用包装工具的先决条件
若要了解有关如何获取先决条件的详细信息，请参阅[如何获取适用于 iOS 的 Intune 应用包装工具的先决条件](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/)博客文章。

|要求|更多信息|
|---------------|--------------------------------|
|支持的操作系统和工具集 | 必须在运行 OS X 10.8.5 或更高版本的 macOS 计算机上运行应用包装工具，并安装 XCode 工具集版本 5 或更高版本。|
|签名证书和预配配置文件 | 你必须有 Apple 签名证书和预配配置文件。 请参阅 [Apple 开发人员文档](https://developer.apple.com/)。|
|使用应用包装工具处理应用  |应用必须由你公司或独立软件供应商 (ISV) 开发并签名。 你无法使用该工具处理 Apple Store 中的应用。 应用必须针对 iOS 8.0 或更高版本编写。 应用还必须是地址无关可执行文件 (PIE) 格式。 有关 PIE 格式的详细信息，请参阅 Apple 开发人员文档。 最后，应用的扩展名必须是 **.app** 或 **.ipa**。|
|工具无法处理的应用 | 加密应用、未签名应用和带有扩展文件属性的应用。|
|设置应用权利|在包装应用之前，必须设置权利，以便为应用提供除平常所授权限和功能以外的其他权限和功能。 有关说明，请参阅[设置应用权利](#setting-app-entitlements)。|

## <a name="install-the-app-wrapping-tool"></a>安装应用包装工具

1.  将应用包装工具文件从 [GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) 下载到 macOS 计算机。

2.  双击 **Microsoft Intune App Wrapping Tool for iOS.dmg**。 将出现“最终用户许可协议 (EULA)”窗口。 仔细阅读该文档。

3. 选择“同意”接受 EULA，这会将包装载到计算机。

4.  打开 **IntuneMAMPackager** 文件夹，并将其内容保存到你的 macOS 计算机。 你现已准备好运行应用包装工具。

## <a name="run-the-app-wrapping-tool"></a>运行应用包装工具

### <a name="use-terminal"></a>使用终端

打开 macOS 终端程序并导航到保存应用包装工具文件的文件夹。 可执行工具名为 IntuneMAMPackager，位于 IntuneMAMPackager/Contents/MacOS。 按如下所示运行命令：

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]
```

> [!NOTE]
> 如下表所示，某些参数是可选的。

**示例：**以下示例命令在名为 MyApp.ipa 的应用上运行应用包装工具。 指定签名证书的预配配置文件和 SHA-1 哈希，并用于对已包装的应用签名。 创建输出应用 (MyApp_Wrapped.ipa)，且将其存储在桌面文件夹中。

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB  -v true
```

### <a name="command-line-parameters"></a>命令行参数
可将以下命令行参数用于应用包装工具：

|属性|如何使用它|
|---------------|--------------------------------|
|**-i**|`<Path of the input native iOS application file>`。 文件名必须以 .app 或 .ipa 结尾。 |
|**-o**|`<Path of the wrapped output application>` |
|**-p**|`<Path of your provisioning profile for iOS apps>`|
|**-c**|`<SHA1 hash of the signing certificate>`|
|**-h**|在应用包装工具可用的命令行属性上显示详细的使用情况信息。|
|**-v**|（可选）将详细信息输出到控制台。|
|**-e**| （可选）使用此标志可使应用包装工具在处理应用的过程中删除缺失的权利。 有关更多详细信息，请参阅“设置应用权利”。|
|**-xe**| （可选）打印应用中的 iOS 扩展，以及使用这些扩展需要哪些权利的相关信息。 有关更多详细信息，请参阅“设置应用权利”。 |
|**-x**| （可选）`<An array of paths to extension provisioning profiles>`。 如果应用需要扩展预配配置文件，使用此项。|
|**-f**|（可选）`<Path to a plist file specifying arguments.>` 如果选择使用 plist 模板指定其余 IntuneMAMPackager 属性（-i、-o 和 -p），使用 [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) 前的此标志。 请参阅“使用 plist 输入参数”。 |
|**-b**|（可选）如果希望已包装的输出应用与输入应用的绑定版本相同，使用不带参数的 -b（不推荐）。 <br/><br/> 如果希望已包装的应用具有自定义 CFBundleVersion，使用 `-b <custom bundle version>`。 如果选择指定自定义 CFBundleVersion，建议以最低有效组件递增本机应用的 CFBundleVersion，例如 1.0.0 -> 1.0.1。 |

### <a name="use-a-plist-to-input-arguments"></a>使用 plist 输入参数
一种运行应用包装工具的简单方法是将所有命令参数置于 [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) 文件中。 Plist 是一种类似于 XML 的文件格式，可使用它通过窗体界面输入命令行参数。

在 IntuneMAMPackager/Contents/MacOS 文件夹中，使用文本编辑器或 Xcode 打开 `Parameters.plist`（一个空白 plist 模板）。 为以下项输入参数：

| Plist 项 |  默认值| 注意 |
|------------------|--------------|-----|
| 输入应用程序包路径  |empty| 与 -i 相同|
| 输出应用程序包路径 |empty| 与 -o 相同|
| 预配配置文件路径 |empty| 与 -p 相同|
| SHA-1 证书哈希 |empty| 与 -c 相同|
| 已启用详情 |false| 与 -v 相同|
| 删除缺失的权利 | false| 与 -c 相同|
| 防止默认生成 |false | 相当于使用不带参数的 -b|
|生成字符串替代 | empty| 已包装输出应用的自定义 CFBundleVersion |
|扩展预配配置文件路径 | empty| 应用的一系列扩展预配配置文件。


将 IntuneMAMPackager 与 plist 一起作为唯一参数运行：

```bash
./IntuneMAMPackager –f Parameters.plist
```

### <a name="post-wrapping"></a>包装后

包装过程完成后，将显示消息“应用程序已成功包装”。 如果出错，请参阅[错误消息](#error-messages-and-log-files)以寻求帮助。

包装的应用已保存在你之前指定的输出文件夹内。 可将应用上传到 Intune 管理控制台并将其与移动应用程序管理策略相关联。

> [!IMPORTANT]
> 上传已包装应用时，若已向 Intune 部署了较旧版本（已包装或本机）的应用，则可尝试更新旧版本应用。 若出现错误，将该应用作为新应用上传并删除旧版本。

现在便可以将应用部署到用户组，并将应用保护策略定向到该应用。 该应用可以在使用所指定的应用保护策略的设备上运行。

## <a name="error-messages-and-log-files"></a>错误消息和日志文件
使用以下信息可排查应用包装工具出现的问题。

### <a name="error-messages"></a>错误消息
如果应用包装工具失败，将在控制台显示以下错误消息之一：

|错误消息|更多信息|
|-----------------|--------------------|
|你必须指定有效的 iOS 配置文件。|配置文件可能无效。 检查以确保具有正确的设备权限，以及针对开发或分发的正确配置文件。 配置文件可能已过期。|
|指定有效的输入应用程序名称。|确保你指定的输入应用程序名称正确。|
|指定输出应用程序的有效路径。|确保你指定的输出应用程序路径存在且正确。|
|指定有效的输入配置文件。|确保你提供了有效的配置文件名称和扩展名。 你的预配配置文件可能没有授权，或你可能没有包括 –p 命令行选项。|
|未找到你指定的输入应用程序。 指定有效的输入应用程序名称和路径。|确保你的输入应用路径有效且存在。 确保输入应用在指定的位置。|
|未找到你指定的输入配置文件。 指定有效的输入配置文件。|确保输入配置文件的路径有效，并且你指定的文件存在。|
|未找到你指定的输出应用程序文件夹。 指定输出应用程序的有效路径。|确保你指定的输出路径有效且存在。|
|输出应用没有 **.ipa** 扩展名。|应用包装工具仅接受扩展名为 **.app** 和 **.ipa** 的应用。 确保你的输出文件的扩展名有效。|
|指定了无效的签名证书。 指定有效的 Apple 签名证书。|确保你从 Apple 开发人员门户下载了正确的签名证书。 证书可能已过期，或可能缺少公钥或私钥。 如果 Apple 证书和预配配置文件可以正确地在 Xcode 内为应用签名，则它们对应用包装工具是有效的。|
|你指定的输入应用程序无效。 指定有效的应用程序。|确保你有编译为的“.app”或“.ipa”的有效 iOS 应用程序。|
|你指定的输入应用程序已加密。 指定有效的未加密应用程序。|应用包装工具不支持加密的应用。 提供未加密的应用。|
|你指定的输入应用程序不是地址无关可执行文件 (PIE) 格式。 指定有效的 PIE 格式应用程序。|地址无关可执行文件 (PIE) 应用运行时可在随机内存地址进行加载。 这对安全性有益。 有关安全优势的详细信息，请参阅 Apple 开发人员文档。|
|你指定的输入应用已包装。 指定有效的未包装应用程序。|你无法处理本工具已经处理过的应用。 如果你想要再次处理应用，请使用原版应用运行本工具。|
|你指定的输入应用程序未签名。 指定已签名的有效应用程序。|应用包装工具需要已签名的应用。 咨询开发人员文档以了解如何对已包装的应用签名。|
|你指定的输入应用程序必须为 .ipa 或 .app 格式。|应用包装工具仅接受 .app 或 .ipa 扩展名。 确保你的输入文件的扩展名有效，并且编译为的“.app”或“.ipa”文件。|
|你指定的输入应用已包装，并且为最新的策略模板版本。|应用包装工具将不会用最新的策略模板版本重新包装现有的已包装应用。|
|警告：你没有指定 SHA1 证书哈希。 确保你的已包装应用程序在部署前已签名。|确保 –c 命令行标志后指定了有效的 SHA1 哈希。 |

### <a name="log-files-for-the-app-wrapping-tool"></a>应用包装工具的日志文件
使用应用包装工具包装的应用生成写入 iOS 客户端设备控制台的日志。 在对应用程序存在疑问且如果该问题与应用包装工具有关并需要进行确定时，此信息有用。 若要检索此信息，请使用以下步骤：

1.  通过运行应用，再现该问题。

2.  通过按照 Apple 的 [调试已部署的 iOS 应用](https://developer.apple.com/library/ios/qa/qa1747/_index.html)说明操作，收集控制台输出。

3.  通过各控制台输入以下脚本，筛选应用限制输出的已保持的日志：

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    你可以将筛选后的日志提交给 Microsoft。

    > [!NOTE]
    > 在日志文件中，“内部版本”代表 Xcode 的内部版本。

    包装的应用也将向用户提供在应用损坏后直接通过电子邮件从设备发送日志的选项。 用户可以将日志发送给你进行检查，并在必要时转发给 Microsoft。


### <a name="certificate-provisioning-profile-and-authentication-requirements"></a>证书、预配配置文件和身份验证要求

适用于 iOS 的应用包装工具必须满足一些要求才能确保功能的完整性。

|要求|详细信息|
|---------------|-----------|
|iOS 预配配置文件|将预配配置文件包括在内之前，确保它有效。 处理 iOS 应用时，应用包装工具不会检查预配配置文件是否已过期。 如果指定了过期的配置文件，应用包装工具将包括过期的配置文件，并且在将应用安装到 iOS 设备之前，你将无法知道存在问题。|
|iOS 签名证书|指定签名证书前，请确保其有效。 处理 iOS 应用时，该工具不会检查证书是否已过期。 如果提供了过期证书的哈希，工具将对应用进行处理并签名，但是应用将无法安装在设备上。<br /><br />确保提供用于对已包装应用进行签名的证书在预配配置文件中存在匹配项。 如果预配配置文件中存在提供用于对已包装应用程序进行签名的证书的匹配项，则该工具不会进行验证。|
|身份验证|设备必须具有 PIN 以使加密起作用。 在部署了已包装应用的设备上，单击设备上的状态栏将要求用户使用工作或学校帐户重新登录。 已包装应用中的默认策略是“重新启动时进行身份验证”。 iOS 通过退出应用然后重新启动来处理任何外部通知（例如电话呼叫）。


## <a name="setting-app-entitlements"></a>设置应用权利
在包装应用之前，可以授予“权利”，以便为应用提供其他权限和功能，使其能够执行比一般情况下更多的操作。 *权利文件*在代码签名过程中用于指定应用内的特殊权限（例如，对共享密钥链的访问权限）。 在应用开发过程中，会在 Xcode 内启用称为“功能”的特定应用服务。 启用后，功能即反映在权利文件中。 有关权利和功能的详细信息，请参阅 iOS 开发人员库中的[添加功能](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html)。 有关支持的功能的完整列表，请参阅[支持的功能](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html)。

### <a name="supported-capabilities-for-the-app-wrapping-tool-for-ios"></a>适用于 iOS 的应用包装工具支持的功能

|功能|描述|推荐指南|
|--------------|---------------|------------------------|
|应用组|使用应用组可让多个应用访问共享容器，并支持应用之间的其他进程间通信。<br /><br />若要启用应用组，请打开“功能”窗格，并单击“应用组”中的“开”。 你可以添加应用组，也可以选择现有应用组。|使用应用组时，请使用反向 DNS 表示法：<br /><br />*group.com.companyName.AppGroup*|
|后台模式|启用后台模式后，iOS 应用可以在后台继续运行。||
|数据保护|数据保护可提高 iOS 应用存储在磁盘上的文件的安全级别。 数据保护使用特定设备提供的内置加密硬件，将文件以加密格式存储在磁盘上。 你的应用需预配为使用数据保护。||
|应用内购买|应用内购买直接将应用商店嵌入用户的应用中，允许用户连接到应用商店并且安全地处理用户付款。 可使用应用内购买收取有关增强功能或应用可用的其他内容的付款。||
|密钥链共享|启用密钥链共享后，你的应用可以与你的团队开发的其他应用共享密钥链中的密码。|使用密钥链共享时，请使用反向 DNS 表示法：<br /><br />*com.companyName.KeychainGroup*|
|个人 VPN|启用个人 VPN 后，你的应用可以使用网络扩展框架来创建和控制自定义系统 VPN 配置。||
|推送通知|Apple Push Notification 服务 (APNs) 可让不在前台运行的应用通知用户，它有关于该用户的信息。|若要使推送通知正常工作，需使用应用特定的预配配置文件。<br /><br />按照 [Apple 开发人员文档](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html)中的步骤操作。|
|无线附件配置|启用无线附件配置可向项目添加外部附件框架，且可让应用设置 MFi Wi-Fi 附件。||

### <a name="steps-to-enable-entitlements"></a>权利启用步骤

1.  启用应用中的功能：

    a.  在 Xcode 中，转到应用的目标，并单击“功能”。

    b。  打开相应的功能。 有关每项功能以及如何确定正确值的详细信息，请参阅 iOS 开发人员库中的[添加功能](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html)。

    c.  记下在此过程中创建的任何 ID。

    d.  生成要包装的应用并对其签名。

2.  启用预配配置文件中的权利：

    a.  登录到 Apple 开发人员会员中心。

    b。  为应用创建预配配置文件。 有关说明，请参阅 [How to Obtain the Prerequisites for the Intune App Wrapping Tool for iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/)（如何获取 Intune App Wrapping Tool for iOS 的先决条件）。

    c.  在预配配置文件中，启用与应用中相同的权利。 你需要提供在应用开发过程中指定的相同 ID。

    d.  完成预配配置文件向导并下载你的文件。

3.  确保已经满足所有先决条件，然后对应用进行包装。

### <a name="troubleshoot-common-errors-with-entitlements"></a>排查与权利相关的常见错误
如果适用于 iOS 的应用包装工具显示权利错误，请尝试下列故障排除步骤。

|问题|原因|解决方法|
|---------|---------|--------------|
|无法分析从输入应用程序生成的权利。|应用包装工具无法读取从应用提取的权利文件。 权利文件的格式可能不正确。|检查应用的权利文件。 以下说明将介绍如何执行此操作。 检查权利文件时，请检查所有格式不正确的语法。 该文件应为 XML 格式。|
|预配配置文件中缺少权利（已列出缺少的权利）。 使用具有这些权利的预配配置文件对应用重新封装。|预配配置文件中启用的权利与应用中启用的功能不匹配。 与特定功能（如应用组和密钥链访问）相关联的 ID 也存在这种不匹配。|通常情况下，你可以创建一个新的预配配置文件，在其中启用与应用相同的功能。 如果配置文件和应用之间的 ID 不匹配，应用包装工具将更换 ID（如果能）。 如果新建预配配置文件后仍然收到此错误，可以尝试使用 –e 参数从应用中删除权利（请参阅“使用 –e 参数从应用中删除权利”部分）。|

### <a name="find-the-existing-entitlements-of-a-signed-app"></a>查找已签名应用的现有权利
若要查看已签名应用和预配配置文件的现有权利，请执行以下操作：

1.  找到 .ipa 文件并将其扩展名更改为 .zip。

2.  展开该 .zip 文件。 这将生成一个包含 .app 包的 Payload 文件夹。

3.  使用 codesign 工具检查 .app 包上的权利，其中 `YourApp.app` 是 .app 包的实际名称：

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```

4.  使用安全工具检查应用的嵌入式预配配置文件的权利，其中 `YourApp.app` 是 .app 包的实际名称。

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```

### <a name="remove-entitlements-from-an-app-by-using-the-e-parameter"></a>使用 – e 参数从应用中删除权利
此命令将删除不在权利文件中的应用中的任何已启用功能。 如果删除应用正在使用的功能，它会中断你的应用。 你可能会删除丢失功能的一个情况示例是拥有一个默认具有所有功能的供应商生产应用。

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## <a name="security-and-privacy-for-the-app-wrapping-tool"></a>应用包装工具的安全和隐私
使用应用包装工具时，请使用以下安全和隐私的最佳做法。

-   指定的签名证书、预配配置文件和业务线应用必须位于运行应用包装工具的同一台 macOS 计算机上。 如果文件在 UNC 路径上，确保可以从 macOS 计算机上访问这些文件。 路径必须受到 IPsec 和 SMB 签名的保护。

    导入到管理控制台中的已包装应用程序应位于你在其上运行该工具的同一计算机上。 如果文件在 UNC 路径上，确保它可以在运行管理控制台的计算机上访问。 路径必须受到 IPsec 和 SMB 签名的保护。

-   从 GitHub 存储库下载应用包装工具的环境必须受到 IPsec 和 SMB 签名的保护。

-   处理的应用来源必须值得信赖，以确保不会受到攻击。

-   确保你在应用包装工具中指定的输出文件夹是安全的，尤其当它是远程文件夹时。

-   包含文件上传对话框的 iOS 应用可以允许用户规避应用于应用的剪切、复制和粘贴限制。 例如，用户可能使用文件上载对话框来上载应用数据的屏幕截图。

-   在你的设备上从包装的应用中监视文档文件夹时，可能会看到一个名为 .msftintuneapplauncher 的文件夹。 如果更改或删除了该文件，则可能影响受限制应用的正确运行。

### <a name="see-also"></a>另请参阅
- [决定如何使用 Microsoft Intune 为移动应用程序管理准备应用](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [使用 Microsoft Intune 策略管理设备上的设置和功能](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [使用 SDK 启用针对移动应用程序管理的应用](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Nov16_HO4-->


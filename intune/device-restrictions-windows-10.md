---
title: "适用于 Windows 10 的 Intune 设备限制设置"
titleSuffix: Intune Azure preview
description: "Intune Azure 预览版：了解可用来控制 Windows 10 设备上的设备设置和功能的 Intune 设置。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 88910c6628bb356e4a757cbdb4cf63b0acf60040
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017


---

# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune 中的 Windows 10 及更高版本设备限制设置

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="general"></a>常规
-     **屏幕捕获（仅限移动版）**- 让用户以图像形式捕获设备屏幕。
-     **复制和粘贴（仅限移动设备）** - 允许设备上应用间的复制和粘贴操作。
-     **手动注销** - 允许用户手动从设备中删除工作区帐户。
-     **手动安装根证书（仅限移动版）**- 阻止用户手动安装根证书和中间 CAP 证书。
-     **诊断数据提交** - 可能的值有：
    -         **无** - 不将数据发送给 Microsoft
    -         **基本** - 将有限的信息发送给 Microsoft
    -         **增强** - 将增强的诊断数据发送给 Microsoft
    -         **完全** - 发送与“增强”相同的数据，外加有关设备状态的其他数据
-     **相机** - 允许或阻止使用设备上的相机。
-     **OneDrive 文件同步** - 阻止设备将文件同步到 OneDrive。
-     **可移动存储** - 指定外部存储设备（如 SD 卡）是否可以与该设备结合使用。
-     **地理位置** - 指定设备是否可以使用位置服务信息。
-     **Internet 共享** - 允许在设备上使用 Internet 连接共享。
-     **手机重置** - 控制用户是否可以在设备上恢复出厂设置。
-     **USB 连接（仅限移动版）**- 控制设备是否可以通过 USB 连接访问外部存储设备。
-     **防盗模式（仅限移动版）**- 配置是否启用 Windows 防盗模式。
-     **操作中心通知（仅限移动版）**- 启用或禁用设备锁定屏幕上的操作中心通知（仅限 Windows 10 移动版）。
-     **Cortana** - 启用或禁用 Cortana 语音助手。
-     **语音录制（仅限移动版）**- 允许或阻止使用设备的语音录音机。
-     **电源和睡眠设置修改（仅限桌面版）**- 阻止最终用户更改设备上的电源和睡眠设置。
-     **区域设置修改（仅限桌面版）**- 阻止最终用户更改设备上的区域设置。
-     **语言设置修改（仅限桌面版）**- 阻止最终用户更改设备上的语言设置。
-     **系统时间修改** - 阻止最终用户更改设备日期和时间。
-     **设备名称修改** - 阻止最终用户更改设备名称。
-     **添加配置包** - 阻止安装配置包的运行时配置代理。
-     **添加配置包** - 阻止删除配置包的运行时配置代理。
-     **设备发现** - 阻止设备被其他设备发现。
-     **任务切换器（仅限移动版）**- 阻止设备上的任务切换器。
-     **SIM 卡错误对话框（仅限移动版）**- 阻止在未检测到 SIM 卡时在设备上显示错误消息。


## <a name="password"></a>Password
-     **密码** - 需要最终用户输入密码才能访问设备。
    -     **所需的密码类型** - 指定密码是否只能是数字或字母数字。
    -     **最短密码长度** - 仅适用于 Windows 10 移动版。
    -     **擦除设备前的登录失败次数** - 对于运行 Windows 10 的设备：如果该设备已启用 BitLocker，在超过指定的登录失败次数后将进入 BitLocker 恢复模式。 如果该设备未启用 BitLocker，则不会应用此设置。
对于运行 Windows 10 移动版的设备：超过指定的登录失败次数后，将擦除设备。
    -     **屏幕锁定前的最大非活动状态分钟数** - 指定锁定屏幕前，设备必须处于空闲状态的时间长度。
    -     **密码过期（天数）** - 指定必须更改设备密码之前的时间长度。
    -     **防止重用以前的密码** - 指定设备记住的以前用过的密码数目。
    -     **设备从空闲状态返回时需要输入密码** - 指定用户必须输入密码以解锁设备（仅限 Windows 10 移动版）。
-     **加密** - 启用对目标设备的加密（仅限 Windows 10 移动版）。

## <a name="personalization"></a>个性化设置

-     **桌面背景图片 URL（仅限桌面版）**- 指定将用作 Windows 桌面墙纸的图片（格式为 PNG、JPG 或 JPEG）的 URL。 用户将无法更改此设置。

## <a name="locked-screen-experience"></a>锁定屏幕体验

-     **锁定屏幕图片 URL（仅限桌面版）**- 指定将用作 Windows 锁定屏幕墙纸的图片（格式为 PNG、JPG 或 JPEG）的 URL。 用户将无法更改此设置。


## <a name="app-store"></a>App Store

-     **应用商店（仅限移动版）** - 在 Windows 10 移动设备上启用或阻止使用应用商店。
-     **自动更新应用商店的应用** - 允许自动更新从 Windows 应用商店安装的应用。
-     **受信任的应用安装** - 允许对使用受信任的证书签名的应用进行旁加载。
-     **开发人员解锁** - 允许 Windows 开发人员设置，如允许最终用户修改旁加载的应用。
-     **共享用户应用数据** - 允许应用在同一设备上的不同用户之间共享数据。
-     **仅使用专用存储** - 启用此选项，仅允许最终用户从你的专用存储下载应用。
-     **存储初次的应用启动** - 用于禁用设备上预安装或从 Windows 应用商店下载的所有应用。
-     **在系统卷上安装应用数据** - 阻止应用在设备的系统卷上存储数据。
-     **在系统驱动器上安装应用** - 阻止应用在设备的系统驱动器上存储数据。
-     **游戏 DVR（仅限桌面版）**- 配置是否允许游戏的录制和广播。



## <a name="edge-browser"></a>Microsoft Edge 浏览器
-     **Microsoft Edge 浏览器（仅限移动版）** - 允许在设备上使用 Microsoft Edge Web 浏览器。
-     **SmartScreen** - 启用或禁用阻止欺诈网站的 SmartScreen。
-     **发送 do-not-track 标头** - 配置 Microsoft Edge 浏览器，将“不跟踪”标头发送到用户访问的网站。
-     **Cookie** - 允许浏览器将 Internet Cookie 保存到设备。
-     **JavaScript** - 允许脚本（如 Javascript）在 Microsoft Edge 浏览器中运行。
-     **弹出窗口** - 阻止浏览器中的弹出窗口（仅适用于 Windows 10 桌面版）。
-     **搜索建议** - 允许搜索引擎在你键入搜索短语时建议站点。
-     **将 Intranet 流量发送到 Internet Explorer** - 允许用户在 Internet Explorer 中打开 Intranet 网站（仅适用于 Windows 10 桌面版）。
-     **自动填充** - 允许用户更改浏览器中的自动完成设置（仅适用于 Windows 10 桌面版）。
-     **密码管理器** - 启用或禁用 Microsoft Edge 密码管理器功能。
-     **企业模式站点列表位置** - 指定在哪个位置可找到以企业模式打开的网站的列表。 用户无法编辑此列表。<br>（仅限 Windows 10 桌面版）。
-     **开发人员工具** - 阻止最终用户打开 Edge 开发人员工具。
-     **扩展** - 阻止最终用户在设备上安装 Edge 扩展。
-     **InPrivate 浏览** - 阻止最终用户打开 InPrivate 浏览会话。
-     **首次运行 URL** - 输入 Edge 浏览器首次运行时将要打开的 URL（仅限移动版）。
-     **主页** - 添加将用作 Edge 浏览器中的主页的网站列表（仅限桌面版）。
-     **阻止访问关于标志** - 阻止最终用户访问 Edge 中包含开发人员和实验设置的 about:flags 页。
-     **智能屏幕提示替代** - 允许最终用户跳过有关潜在的恶意网站的 SmartScreen 筛选器警告。
-     **文件的智能屏幕提示替代** - 允许最终用户跳过有关下载潜在的恶意文件的 SmartScreen 筛选器警告。
-     **WebRtc localhost IP 地址** - 在使用 Web RTC 协议拨打电话时，阻止显示用户 localhost IP 地址。
-     **默认搜索引擎** - 指定要使用的默认搜索引擎。 最终用户可以随时更改此值。

## <a name="search"></a>搜索
- **安全搜索（仅限移动版）**- 控制 Cortana 在搜索结果中筛选成人内容的方式。 可以选择“严格”或“中等”或允许最终用户选择自己的设置。

## <a name="cloud-and-storage"></a>云和存储
-     **Microsoft 帐户** - 使用户可以将 Microsoft 帐户与设备关联。
-     **非 Microsoft 帐户** - 使用户可以将电子邮件帐户添加到不与 Microsoft 帐户相关联的设备。
-     **Microsoft 帐户的设置同步** - 允许设备和应用设置与 Microsoft 帐户关联以在设备之间进行同步。

## <a name="cellular-and-connectivity"></a>手机网络和连接性
-     **数据漫游** - 允许在访问数据时进行网络之间的漫游。
-     **通过手机网络使用 VPN** - 控制设备在连接到手机网络时是否能够访问 VPN 连接。
-     **通过手机网络漫游 VPN** - 控制设备在手机网络上漫游时是否能够访问 VPN 连接。
-     **蓝牙** - 控制用户是否可以在设备上启用和配置蓝牙。
-     **蓝牙可发现性** - 允许其他已启用蓝牙的设备可发现此设备。
-     **蓝牙广告** - 允许设备通过蓝牙接收广告。
-     **设备蓝牙名称** - 使你能够指定设备的蓝牙名称。
-     **NFC** - 允许用户在设备上启用和配置近场通信功能。
-     **Wi-Fi** - 允许用户在设备上启用和配置 Wi-Fi（仅限 Windows 10 移动版）。
-     **自动连接到 Wi-Fi 热点** - 可让设备自动连接到免费 Wi-Fi 热点并自动接受该连接的任何条款和条件。
-     **手动配置 Wi-Fi** - 控制用户是否可以配置自己的 Wi-Fi 连接或是否只能使用 Wi-Fi 配置文件配置的连接（仅限 Windows 10 移动版）。
-     **Wi-Fi 扫描间隔** - 指定设备扫描 Wi-Fi 网络的频率。

## <a name="control-panel-and-settings"></a>控制面板和设置

-     **设置应用** - 阻止访问 Windows 设置应用。
    -     **系统** - 阻止访问设置应用的系统区域。
    -     **设备** - 阻止访问设置应用的设备区域。
    -     **网络 Internet** - 阻止访问设置应用的网络和 Internet 区域。
    -     **个性化设置** - 阻止访问设置应用的个性化设置区域。
    -     **帐户** - 阻止访问设置应用的帐户区域。
    -     **时间和语言** - 阻止访问设置应用的时间和语言区域。
    -     **轻松访问** - 阻止访问设置应用的轻松访问区域。
    -     **隐私** - 阻止访问设置应用的隐私区域。
    -     **更新安全** - 阻止访问设置应用的更新和安全区域。

## <a name="defender"></a>Defender

-     **实时监控** - 启用对恶意软件、间谍软件和其他不需要的软件的实时扫描。
-     **行为监控** - 允许 Defender 检查设备上是否存在某些已知模式的可疑活动。
-     **网络检查系统 (NIS)** - 网络检查系统 (NIS) 通过使用 Microsoft Endpoint Protection 中心的已知漏洞的签名帮助检测和阻止恶意流量，从而保护设备免受基于网络的攻击。
-     **扫描所有下载** - 控制 Defender 是否扫描从 Internet 下载的所有文件。
-     **扫描 Microsoft Web 浏览器中加载的脚本** - 允许 Defender 扫描在 Internet Explorer 中使用的脚本。
-     **Defender 的最终用户访问权限** - 控制是否对最终用户隐藏 Windows Defender 用户界面。
此设置更改后，将在最终用户的 PC 下次重启时生效。
-     **签名更新间隔（小时）** - 指定 Defender 检查新签名文件的时间间隔。
-     **监视文件和程序活动** - 允许 Defender 监视设备上的文件和程序活动。
-     **删除已隔离恶意软件之前的天数** - 允许 Defender 按指定的天数继续跟踪已解决的恶意软件，以便可以手动检查之前受影响的设备。 如果你将天数设置为 **0**，则恶意软件将保留在隔离文件夹中，并且不会自动删除。
-     **在扫描期间限制 CPU 使用率** - 可让你限制允许扫描使用的 CPU 量（从 **1** 到 **100**）。
-     **扫描存档文件** - 允许 Defender 扫描存档的文件（如 Zip 或 Cab 文件）。
-     **扫描传入的电子邮件** - 允许 Defender 在电子邮件到达设备时扫描它们。
-     **完全扫描期间扫描可移动驱动器** - 允许 Defender 扫描可移动驱动器（如 U 盘）。
-     **完全扫描期间扫描映射的网络驱动器** - 允许 Defender 扫描映射网络驱动器上的文件。<br>如果驱动器上的文件是只读的，则 Defender 将无法删除在它们中找到的任何恶意软件。
-     **扫描从网络文件夹打开的文件** - 允许 Defender 扫描共享网络驱动器上的文件（例如，从 UNC 路径访问的那些文件）。
如果驱动器上的文件是只读的，则 Defender 将无法删除在它们中找到的任何恶意软件。
-     **Cloud 保护** - 允许或阻止 Microsoft Active Protection Service 接收来自你管理的设备的恶意软件活动的相关信息。 此信息用于在将来改进本服务。
-     **在示例提交前提示用户** - 控制是否自动向 Microsoft 发送可能需要 Microsoft 的进一步分析以确定其是否为恶意的文件。
-     **执行日常快速扫描的时间** - 允许计划每日在你选择的时间里发生的快速扫描。
-     **要执行的系统扫描类型** - 允许计划系统扫描时指定要执行的扫描级别。

## <a name="defender-exclusions"></a>Defender 排除项

-     **要从扫描和实时保护排除的文件和文件夹** - 向排除列表添加一个或多个文件和文件夹（如 **C:\Path** 或 **%ProgramFiles%\Path\filename.exe**）。 不会在任何实时或计划的扫描中包括这些文件和文件夹。
-     **要从扫描和实时保护排除的文件扩展名** - 向排除列表添加一个或多个文件扩展名（如 **jpg** 或 **txt**）。 不会在任何实时或计划的扫描中包括具有这些扩展名的任何文件。
-     **要从扫描和实时保护排除的进程** - 向排除列表添加一个或多个类型为 **.exe**、**.com** 或 **.scr** 的进程。 不会在任何实时或计划的扫描中包括这些进程。


## <a name="network-proxy"></a>网络代理

-     **自动检测代理设置** - 启用后，设备将尝试查找 PAC 脚本的路径。
-     **使用代理脚本** - 如果想要指定 PAC 脚本的路径以配置代理服务器，请选择此项。
    -     **设置脚本地址 URL** - 输入想要使用的 PAC 脚本的 URL，以配置代理服务器。
-     **使用手动代理服务器** - 如果想要手动提供代理服务器信息，请选择此项。
    -     **地址** - 输入代理服务器的名称或 IP 地址。
    -     **端口号** - 输入代理服务器的端口号。
    -     **代理例外** - 输入不得使用代理服务器的任何 URL。 请使用分号分隔每一项。
    -     **跳过本地地址的代理服务器** - 如果不想在你的内部网上对本地地址使用代理服务器，请启用此选项。


## <a name="windows-spotlight"></a>Windows 聚焦

-     **Windows 聚焦** - 允许或阻止提供提示和技巧、Windows 锁定屏幕上的消息等功能的 Windows 聚焦。
    -     **Windows 提示** - 使你能够阻止在 Windows 中显示弹出窗口提示。
    -     **使用者功能** - 使你能够阻止开始菜单建议等使用者功能和成员资格通知。

## <a name="display"></a>显示

- **来自无线显示接收方的用户输入** - 阻止来自无线显示接收方的用户输入。
- **此电脑的投影** - 阻止其他设备发现用于投影的电脑。
- **需要用于配对的 PIN** - 在连接到投影设备时需要 PIN。

## <a name="start"></a>启动

- **从任务栏取消固定应用** - 阻止用户从开始菜单取消固定应用。
- **“开始”上的文档** - 隐藏或显示 Windows 开始菜单中的文档文件夹。
- **“开始”上的下载** - 隐藏或显示 Windows 开始菜单中的下载文件夹。
- **“开始”上的文件资源管理器** - 隐藏或显示 Windows 开始菜单中的文件资源管理器应用。
- **“开始”上的家庭组** - 隐藏或显示 Windows 开始菜单中的家庭组文件夹。
- **“开始”上的音乐** - 隐藏或显示 Windows 开始菜单中的音乐文件夹。
- **“开始”上的网络** - 隐藏或显示 Windows 开始菜单中的网络文件夹。
- **“开始”上的个人文件夹** - 隐藏或显示 Windows 开始菜单中的个人文件夹。
- **“开始”上的图片** - 隐藏或显示 Windows 开始菜单中的图片文件夹。
- **“开始”上的设置** - 隐藏或显示 Windows 开始菜单中的设置应用。
- **“开始”上的视频** - 隐藏或显示 Windows 开始菜单中的视频文件夹。
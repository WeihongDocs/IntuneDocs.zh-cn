---
title: "Intune 最终用户应用的 UI 更新"
description: "了解 Intune 中针对最终用户设备上可用的应用所做的 UI 更改。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 73b43084c28436cb8a7e866dcee2d52694c60f5c
ms.openlocfilehash: 2706f5d615cf9b14bd3126d89c07b0dfa5e9a5c1
ms.contentlocale: zh-cn
ms.lasthandoff: 06/16/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Intune 最终用户应用的 UI 更新
了解此版本的 Microsoft Intune 中，针对最终用户会看到的应用所做的 UI 更新。 这有助于与用户之间的通信以及用于支持部署的已创建的任何更新自定义文档。 还有助于了解如何在用户使用公司门户寻求支持人员的帮助和支持时更好地解决用户面临的任何问题。

## <a name="coming-soon-in-the-ui"></a>即将在 UI 中推出的内容
以下是我们通过更新用户界面提升用户体验的各种方法的计划。

> [!Note]
> 请注意，以下图像可能是预览版，发布的产品可能与当前版本有所不同。

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>改进了所有平台上跨公司门户应用的登录体验<!--User Story 1132123-->

我们宣布将在接下来的几个月内推出一项更新，该更新将提升适用于 Android、iOS 和 Windows 的 Intune 公司门户应用的登录体验。 当 Azure AD 进行此更改时，新的用户体验将自动在公司门户应用的所有平台上显现。 此外，用户可以使用生成的一次性验证码从其他设备立即登录到公司门户。 当用户需要在没有凭据的情况下登录时，这尤为有用。  

下面，将向你介绍使用凭据进行登录的以前的登录体验和新登录体验，以及从其他设备进行登录的新登录体验。

__以前的登录体验__

![公司门户登录页，网站的图形表示形式前面显示一个人形图标。 下面是“登录”按钮。 底部的链接指向 Microsoft 隐私和 Cookie 信息。](./media/cp_ios_aad_signin_before_1704_001.png)

![点击“登录”后，用户在此页上输入其凭据，系统要求输入用户的电子邮件和密码，还提供其他方法以解决密码出错的情况。](./media/cp_ios_aad_signin_before_1704_002.png)

![提供密码后，公司门户应用登录，并通过加载栏进行提示。](./media/cp_ios_aad_signin_before_1704_003.png)

__新的登录体验__

![公司门户登录页，网站的图形表示形式前面显示一个人形图标。 下面是“登录”按钮。 底部的链接指向 Microsoft 隐私和 Cookie 信息。](./media/cp_ios_aad_signin_after_1704_001.png)

![提示用户只提供电子邮件地址，而不是在同一屏幕上同时提供电子邮件和密码。](./media/cp_ios_aad_signin_after_1704_002.png)

![在接受其电子邮件地址之后，提示用户输入密码。](./media/cp_ios_aad_signin_after_1704_003.png)

![在经过身份验证过程后，公司门户应用进行登录，并通过加载栏进行提示。](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__从其他设备登录时的新登录体验__

![公司门户登录页，网站的图形表示形式前面显示一个人形图标。 下面是“登录”按钮。 底部的链接指向 Microsoft 隐私和 Cookie 信息。](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

点击“从其他设备登录”链接。

![通过使用工作计算机的唯一密码访问 aka.ms/devicelogin 页面，然后使用验证码进行登录可获得说明。](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

启动浏览器，然后转到 [https://aka.ms/devicelogin](https://aka.ms/devicelogin)。

![用户工作计算机上用户浏览器的图像，而不是公司门户应用的图像。 显示的“设备登录”页将提示用户输入他们在公司门户应用中收到的验证码。](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

输入在公司门户应用中看到的验证码。 选择“继续”，你将能够使用受贵公司支持的任意方法进行身份验证，如智能卡。

![用户已将唯一代码输入到字段中，“设备登录”站点要求确认 Intune 公司门户是接收授权以进行登录的正确应用。](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![确认页显示用户现在已登录其设备上的公司门户应用，可以关闭此页。](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

公司门户应用将开始进行登录。

![在经过身份验证过程后，公司门户应用进行登录，并通过加载栏进行提示。](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="june-2017"></a>2017 年 6 月

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>新增可轻松删除公司门户的菜单操作 <!--1164569-->
根据用户反馈，适用于 Android 的公司门户应用新添加了一个菜单操作，可启动对设备中公司门户的删除。 此操作可将设备从 Intune 管理中删除，以便用户删除设备中的应用。

![Android 公司门户应用的图像和操作菜单将在右上角打开。 新的“删除公司门户”选项是第三个选项，位于“我的配置文件“和“设置”的下方，以及“条款和条件”、“帮助和反馈”和“关于”的上方。](./media/android_remove_cp_menu_action_after_1705.png)

![在操作菜单中选择新的“删除公司门户”选项后，将出现一个确认对话图像。 该对话将通知用户“删除公司门户，设备将不再由 IT 管理员管理，并且可能删除对公司数据、公司应用和公司电子邮件的访问权限。” 然后，它会要求用户通过选择“是”确认删除“公司门户”应用。](./media/android_remove_cp_menu_confirmation_after_1705.png)

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>对适用于 iOS 的公司门户应用中应用磁贴的改进
我们更新了主页上的应用磁贴设计，以反映你为公司门户设置的品牌颜色。 

**之前**

![更新前适用于 iOS 的公司门户应用图像，显示了“所有应用”、“特别推荐的应用”和“类别”的预设填充符图像。](./media/cp_ios_homepage_before_1705.png)

**之后**

![更新后适用于 iOS 的公司门户应用图像，现在反映了选择任意与组织相关的颜色的功能。](./media/cp_ios_homepage_after_1705.png)

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>适用于 iOS 的公司门户应用现在可使用帐户选取器
如果用户使用工作或学校帐户在其 iOS 设备上登录其他 Microsoft 应用，则他们可能会在首次登录公司门户时看到我们的新帐户选取器。 

![帐户选取器图像，显示了测试用户“Robin Swanson”在他的两个电子邮件地址之间选择。 两个地址下有一个按钮，让用户可以使用不同帐户登录。](./media/cp_ios_multi-account-selector-after-1705.png)

## <a name="april-2017"></a>2017 年 4 月

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Managed Browser 和公司门户的新图标 <!--918433, 918431-->

托管浏览器正在接收 Android 和 iOS 版本应用的更新图标。 新图标将包含更新的 Intune 徽章，使其与企业移动性 + 安全性 (EM+S) 中的其他应用更加一致。

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

公司门户还接收 Android、iOS 和 Windows 版本应用的更新图标，以提高与 EM + S 中其他应用的一致性。 这些图标将在 4 月至 5 月下旬在所有平台中逐步发布。

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Android 公司门户中的登录进度指示器 <!--953374-->

用户启动或恢复应用时，Android 公司门户应用的更新会显示进度指示器。 允许用户访问应用前，指示器将经历以下新状态：开始是“正在连接...”，然后是“正在登录...”，接下来是“正在查看安全要求...”。

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>改进 Windows 10 公司门户应用的应用安装状态 <!--676495-->
现在，Windows 10 公司门户应用在应用详细信息页上提供安装进度栏。 运行 Windows 10 周年更新和更高版本的设备上的现代应用支持此功能。

__之前__
  ![以前版本的加载屏幕的图像，其中状态仅显示“正在安装”。](./media/cp_win10_install_status_before_1704.png)

__之后__
  ![已更新版本的加载屏幕的图像，现在显示安装进度栏。](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>2017 年 2 月

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Android 适用的公司门户应用的最新用户体验<!--621622, announced 1702-->
从 3 月开始，Android 适用的公司门户应用将按照[材料设计指南](https://material.io/guidelines/material-design/introduction.html)来打造更具现代感的外观。 这将改善以下用户体验：

* __颜色__：可以根据自定义调色板对选项卡标头着色。

![左侧为更新之前的 Android 适用的公司门户应用的图像。 右侧为更新之后的 Android 适用的公司门户应用的图像。 两张图像中都选定了“应用”、“设备”和“联系 IT”三个可用选项卡中的“设备”选项卡。](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __界面__：“应用”选项卡上已更新了“特色应用”和“所有应用”按钮。 “搜索”按钮现在是浮动的操作按钮。

![左侧为更新之前的 Android 适用的公司门户应用的图像。 右侧为更新之后的 Android 适用的公司门户应用的图像。 两张图像中都选定了“应用”、“设备”和“联系 IT”三个可用选项卡中的“应用”选项卡。](./media/CP_Android_AppsTab_BeforeAfter.png)

* __导航__：“所有应用”以选项卡形式呈现出“特色”、“所有”和“分类”视图，便于导航。 “联系 IT”已经简化，改善了可读性。

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>2017 年 1 月

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>公司门户网站现代化<!--753980, announced 1701-->
从 2 月开始，公司门户网站将支持针对不具有托管设备的用户的应用。 此网站将使用新的撞色配色方案、动态图和“汉堡菜单” ![（汉堡菜单的小图，该图片现已添加到公司门户网站左上角，](./media/CP_hamburger_menu.png) 它包括了支持人员详细联系信息和现有托管设备的信息），这与 Microsoft 其他产品和服务保持一致。 将重新排列登录页，强调可供用户使用的应用，登录页上具有针对特色应用和最近更新应用的传送。

![左侧是当前版本的公司门户网站的图像，其中包含之前版本的应用、“我的设备”以及“特别推荐”视图和“类别”视图。 右侧是更新版本的公司门户网站的图像，其中包含刷新的应用轮播、“最近发布”的应用列表和更新的“类别”视图。](./media/CP_Website_BeforeAfter_Feb2016.png)


### <a name="see-also"></a>另请参阅
* [Microsoft Intune 博客](http://go.microsoft.com/fwlink/?LinkID=273882)
* [云平台路线图](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Intune 中的新增功能](https://docs.microsoft.com/intune/whats-new)

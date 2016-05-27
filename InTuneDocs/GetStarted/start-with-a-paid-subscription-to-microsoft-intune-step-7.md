---
# required metadata

title: 自定义公司门户 | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# 自定义公司门户
在 [!INCLUDE[wit_iwportal_1](../includes/wit_iwportal_1_md.md)]中，用户可以访问公司数据和执行常见任务，比如注册设备、安装应用，以及查找信息以从 IT 部门获得帮助。

> 当你自定义公司门户时，配置会同时应用于公司门户网站和公司门户应用。

自定义公司门户有助于为最终用户提供熟悉且有帮助的体验。 若要实现此操作，只需以租户或服务管理员的身份登录 [Microsoft Intune 管理员控制台](https://manage.microsoft.com)，选择“管理员” &gt; “公司门户”，然后配置公司门户的设置。

![admin-console-admin-workspace-comp-portal-settings](./media/companyportal.png)

## 公司联系人信息和隐私声明
公司名称显示为公司门户的标题。 联系人信息和详细信息将在公司门户的“联系 IT 部门”屏幕中向用户显示。 当用户单击隐私链接时，将显示隐私声明。

|字段名称|最大长度|更多信息|
    |----------|------------------------|----------------|
    |公司名称|40|此名称显示为公司门户的标题。|
    |IT 部门联系人姓名|40|此名称显示在“联系 IT”页上。|
    |IT 部门的电话号码|20|此联系人号码显示在“联系 IT”页上。|
    |IT 部门的电子邮件地址|40|此联系人地址显示在“联系 IT”页上。 必须以 **alias@domainname.com** 格式输入有效的电子邮件地址|
    |其他信息|120|显示在“联系 IT”页上。|
    |公司隐私声明 URL|79|你可以指定自己的公司隐私声明，当用户从公司门户中单击隐私链接时，该隐私声明将出现。 必须以 https://www.contoso.com 格式输入有效的 URL。|

## 支持联系人
在公司门户向用户显示支持网站，以使他们能够访问在线支持。

|字段名称|最大长度|更多信息|
    |----------|------------------------|----------------|
    |支持网站 URL|150|如果你拥有希望用户可以使用的支持网站，请在此处指定 URL。 该 URL 必须采用 https://www.contoso.com 格式。 如果不指定 URL，则公司门户中的“联系 IT”页上将不会显示支持网站的任何内容。|
    |网站名称|40|此名称是为支持网站的 URL 显示的友好名称。 如果指定支持网站 URL 而不指定友好名称，则公司门户中的“联系 IT”页上将显示“转到 IT 网站”。|

## 公司品牌自定义
你可以使用公司徽标、公司名称、主题颜色和背景来自定义公司门户。

|字段名称|更多信息|
    |----------|----------------|
    |主题颜色|选择要应用于公司门户的主题颜色。|
    |包括公司徽标|如果启用此选项，你可以上传公司徽标以显示在公司门户中。 你可以上传两个徽标：一个在公司门户背景为白色时显示的徽标，以及一个在公司门户背景使用所选主题颜色时使用的徽标。 每个徽标必须是 .png 或 .jpg 文件类型，最大分辨率为 400 x 100 像素，大小等于或小于 750 KB。|
    |为 [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] 公司门户应用选择背景|此设置只影响 [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] 公司门户应用的背景。|


保存更改之后，你可以使用管理控制台的“公司门户”页面底部提供的链接来查看公司门户网站。 无法更改这些链接。 当用户登录时，这些链接将在公司门户中显示你的订阅。

### 后续步骤
祝贺你！ 你刚刚完成了 *Intune 快速入门指南*的步骤 7
>[!div class="step-by-step"]

>[&larr; **创建策略和应用**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)       [**注册设备** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  


<!--HONumber=May16_HO2-->


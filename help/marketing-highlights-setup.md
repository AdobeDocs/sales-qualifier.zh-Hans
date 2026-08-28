---
title: 设置营销亮点
description: 了解如何将Marketo连接到Sales Qualifier，以便代表可以在“营销亮点”中按Marketo的实时活动查看和筛选潜在客户。
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 17bfe0a1ce9b289ed85af0f72ddd089b11cca875
workflow-type: tm+mt
source-wordcount: 675
ht-degree: 1%

---


# 设置营销亮点

营销亮点显示每个潜在客户的实时[!DNL Marketo]活动，如电子邮件打开数和点击数、Web访问数和表单填写数。 本文说明如何连接[!DNL Marketo]实例，以便活动流入中。

>[!IMPORTANT]
>
>要完成此设置，需要访问[!DNL Marketo]中的Adobe Developer Console和&#x200B;**[!UICONTROL 管理员]**。 请与您的Adobe联系人和[!DNL Marketo]管理员合作，完成以下四个部分。

设置分为四个部分：

* A部分：在Adobe Developer Console中创建API凭据。
* B部分：收集Sales Qualifier端点和标识符。
* C部分：在[!DNL Marketo Engage]中配置webhook。
* 第D部分：将webhook添加到触发器Smart Campaign。

安装完成后，用户将在&#x200B;**[!UICONTROL 潜在客户]** > **[!UICONTROL 营销亮点]**&#x200B;上查看和筛选此活动。

## A部分：创建API凭据 {#part-a-create-api-credentials}

这些凭据允许[!DNL Marketo]安全地向Sales Qualifier进行身份验证。

要创建凭据，请执行以下操作：

1. 转到[Adobe Developer Console](https://developer.adobe.com/console/)并使用您的Adobe ID登录。
1. 选择&#x200B;**[!UICONTROL 创建新项目]**，或打开现有项目。
1. 选择&#x200B;**[!UICONTROL 编辑项目]**，将该项目重命名为可识别的项目，如`Sales Qualifier Marketing Highlights`，然后选择&#x200B;**[!UICONTROL 保存]**。
1. 选择&#x200B;**[!UICONTROL 添加API]**，选择&#x200B;**[!UICONTROL Experience Platform API]**，然后选择&#x200B;**[!UICONTROL 下一步]**。
1. 选择&#x200B;**[!UICONTROL OAuth服务器到服务器]**&#x200B;作为身份验证类型，然后选择&#x200B;**[!UICONTROL 下一步]**。

   **[!UICONTROL OAuth服务器到服务器]**&#x200B;允许[!DNL Marketo]直接从服务器调用Sales Qualifier API，无需人员登录。

1. 输入不超过45个字符的凭据名称，如`Sales Qualifier Marketing Highlights Creds`。
1. 选择要关联的产品配置文件，然后选择&#x200B;**[!UICONTROL 保存配置的API]**。
1. 在&#x200B;**[!UICONTROL 连接的凭据]**&#x200B;下，打开&#x200B;**[!UICONTROL OAuth服务器到服务器]**&#x200B;凭据。 选择&#x200B;**[!UICONTROL 检索客户端密钥]**，然后复制&#x200B;**[!UICONTROL 客户端ID]**&#x200B;和&#x200B;**[!UICONTROL 客户端密钥]**。 在[部分C](#part-c-configure-the-marketo-webhook)中使用这些值。

>[!WARNING]
>
>将客户端密钥设为私有。 请将其视为密码，不要通过电子邮件发送。 使用您组织批准的安全渠道与配置webhook的人员共享该渠道。

## B部分：收集您的端点和标识符 {#part-b-gather-your-endpoint-and-identifiers}

[部分C](#part-c-configure-the-marketo-webhook)需要三个值：

* **端点URL** — 您所在地区的Sales Qualifier webhook地址。
* **imsOrg ID** — 贵组织在Adobe Identity Management System (IMS)中的标识符，格式为`{ORG_ID}@AdobeOrg`。
* **沙盒名称** — 您的AEP沙盒的名称与在Sales Qualifier URL中显示的名称（`sname`值）完全相同，而不是在UI中显示的显示名称。 使用小写URL值，例如`prod`，而不是`Prod`。

| 区域 | Webhook端点URL |
| --- | --- |
| 北美洲 | `https://5r6xakp9k3.execute-api.us-east-1.amazonaws.com/prod/external/marketo/signals` |
| EMEA | `https://pc72i8q1k3.execute-api.eu-west-1.amazonaws.com/prod/external/marketo/signals` |
| APAC /澳大利亚 | `https://5cxxxyqlai.execute-api.ap-southeast-2.amazonaws.com/prod/external/marketo/signals` |

{style="table-layout:auto"}

如果您不确定自己的地区、imsOrg ID或沙盒名称，您的Adobe联系人可以确认它们。

## C部分：配置Marketo webhook {#part-c-configure-the-marketo-webhook}

要创建webhook，请执行以下操作：

1. 在[!DNL Marketo]中，选择&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL Webhooks]**。
1. 选择&#x200B;**[!UICONTROL 新建Webhook]**。
1. 将&#x200B;**[!UICONTROL URL]**&#x200B;设置为[B](#part-b-gather-your-endpoint-and-identifiers)部分中的您区域的终结点URL。
1. 将&#x200B;**[!UICONTROL 请求类型]**&#x200B;设置为`POST`。
1. 将&#x200B;**[!UICONTROL 请求令牌编码]**&#x200B;设置为`JSON`。 必须提供此设置。
1. 将下面的有效负载模板粘贴到&#x200B;**[!UICONTROL 模板]**&#x200B;中。 使用[!DNL Marketo]的&#x200B;**[!UICONTROL 插入令牌]**&#x200B;匹配实例中的字段名称。

   >[!NOTE]
   >
   >使用JSON编码时，请勿将字符串令牌包裹在引号中。 [!DNL Marketo]自动添加它们。

   ```json
   {
     "leadId": {{lead.Id:default=0}},
     "email": {{lead.Email Address:default=}},
     "fullName": {{lead.Full Name:default=}},
     "company": {{company.Company Name:default=}},
     "title": {{lead.Job Title:default=}},
     "department": {{lead.Department:default=}},
     "country": {{lead.Country:default=}},
     "score": {{lead.Lead Score:default=0}},
     "rating": {{lead.Lead Rating:default=}},
     "leadStatus": {{lead.Lead Status:default=}},
     "leadSource": {{lead.Lead Source:default=}},
     "isCustomer": {{lead.Is Customer:default=false}},
     "industry": {{company.Industry:default=}},
     "annualRevenue": {{company.Annual Revenue:default=0}},
     "numEmployees": {{company.Num Employees:default=0}},
     "campaignId": {{campaign.id:default=0}},
     "campaignName": {{campaign.name:default=}},
     "programName": {{program.name:default=}},
     "occurredAt": {{system.dateTime:default=}},
     "munchkinId": {{system.munchkinId:default=}},
     "triggerName": {{trigger.Trigger Name:default=}},
     "crmId": {{lead.SFDC ID:default=}},
     "crmType": {{lead.SFDC Type:default=}},
     "crmOwnerEmail": {{lead.Lead Owner Email Address:default=}},
     "crmOwnerFirstName": {{lead.Lead Owner First Name:default=}},
     "crmOwnerLastName": {{lead.Lead Owner Last Name:default=}},
     "attributes": {
       "asset": {{trigger.Name:default=}},
       "link": {{trigger.Link:default=}},
       "subject": {{trigger.Subject:default=}},
       "webPage": {{trigger.Web Page:default=}},
       "category": {{trigger.Category:default=}},
       "details": {{trigger.Details:default=}},
       "sentBy": {{trigger.Sent By:default=}},
       "receivedBy": {{trigger.Received By:default=}},
       "referrer": {{trigger.Referrer:default=}},
       "searchEngine": {{trigger.Search Engine:default=}},
       "searchQuery": {{trigger.Search Query:default=}},
       "imDescription": {{lead.Last Interesting Moment Desc:default=}},
       "imType": {{lead.Last Interesting Moment Type:default=}},
       "imDate": {{lead.Last Interesting Moment Date:default=}},
       "imSource": {{lead.Last Interesting Moment Source:default=}},
       "chatAgentName": {{trigger.Agent Name:default=}},
       "chatAgentEmail": {{trigger.Agent Email:default=}},
       "chatConversationStatus": {{trigger.Conversation Status:default=}},
       "chatConversationSummary": {{trigger.Conversation Summary:default=}},
       "chatGoalName": {{trigger.Goal name:default=}},
       "chatMeetingStatus": {{trigger.meeting status:default=}},
       "chatScheduledFor": {{trigger.Scheduled For:default=}},
       "chatDocumentName": {{trigger.Document Name:default=}},
       "chatDocumentUrl": {{trigger.Document URL:default=}},
       "chatPageUrl": {{trigger.Page URL:default=}}
     }
   }
   ```

1. 选择&#x200B;**[!UICONTROL Webhook操作]** > **[!UICONTROL 设置自定义标头]**，然后使用[部分A](#part-a-create-api-credentials)和[部分B](#part-b-gather-your-endpoint-and-identifiers)中的值添加以下标头：

   | 标头 | 值 |
   | --- | --- |
   | `Content-Type` | `application/json` |
   | `x-client-id` | 您的客户端ID |
   | `x-client-secret` | 您的客户端密码 |
   | `x-gw-ims-org-id` | 您的imsOrg ID |
   | `x-sandbox-name` | 您的沙盒名称 |

   {style="table-layout:auto"}

1. 选择&#x200B;**[!UICONTROL 保存]**。

## D部分：将webhook添加到触发器Smart Campaign {#part-d-add-the-webhook-to-a-trigger-smart-campaign}

将&#x200B;**[!UICONTROL Call Webhook]**&#x200B;流程步骤添加到触发智能营销活动（现有或新步骤）。 智能列表会在该营销策划中触发，从而决定要将哪些活动发送到Sales Qualifier。

要添加webhook，请执行以下操作：

1. 打开现有的触发器Smart Campaign，或创建一个新触发器（**[!UICONTROL 营销活动]** > **[!UICONTROL 新建]** > **[!UICONTROL Smart Campaign]**）。
1. 在&#x200B;**[!UICONTROL 智能列表]**&#x200B;选项卡上，为要发送的活动添加一个或多个触发器，例如&#x200B;**[!UICONTROL 单击电子邮件中的链接]**、**[!UICONTROL 填写表单]**&#x200B;或&#x200B;**[!UICONTROL 访问网页]**。
1. 在&#x200B;**[!UICONTROL 流]**&#x200B;选项卡上，添加&#x200B;**[!UICONTROL 调用Webhook]**&#x200B;步骤，并选择您在[C](#part-c-configure-the-marketo-webhook)部分中创建的webhook。
1. 激活Smart Campaign。

来自该Smart Campaign的活动现在流入Sales Qualifier。 代表可以在&#x200B;**[!UICONTROL 潜在客户]** > **[!UICONTROL 营销亮点]**&#x200B;上查看和筛选此活动。

>[!MORELIKETHIS]
>
>* [管理集成](integrations.md)
>* [潜在客户](prospects.md)
>* [入门](getting-started.md)

---
title: 管理员设置
description: 了解如何管理CRM字段、活动同步、电子邮件选择退出和其他Adobe Marketo限定符管理设置。
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
TQID: 'https://experienceleague.adobe.com/vbtO6I67ZEaZz3oio9InNErvq5D0wjbRxyDZpTq8Lzo'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: CX Enterprise
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
    internal-label: Integrations
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
    internal-label: Administration

internal-label: Administration
source-git-commit: d967b633fcb63c64169d3e3fbf305fd2ff82236d
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 0%
---

# 管理员设置

使用&#x200B;**[!UICONTROL 管理员设置]**&#x200B;配置CRM集成、管理知识中心和配置电子邮件选择退出。

Adobe Marketo限定符连接到Salesforce或Microsoft Dynamics 365。 该连接使Account Qualification Agent (AQA)可以一致地查看潜在客户、客户、联系人、活动和所有者。 Marketo Qualifier还可以将外联活动和选择退出状态写回CRM，并将外联活动与Marketo同步。

要配置CRM连接、字段映射和活动同步，请转到&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 管理员设置]** > **[!UICONTROL CRM连接]**。 标准用户可以使用配置的CRM数据和过滤器，但无法更改这些设置。 若要首次连接CRM，请参阅[开始使用](getting-started.md#connect-your-crm)。

>[!IMPORTANT]
>
>访问&#x200B;**[!UICONTROL 管理员设置]**&#x200B;需要`Marketo Qualifier`和`Marketo Qualifier Admins`用户组的成员资格。

## CRM MCP和嵌入式插件

Marketo限定符可通过以下方式与您的CRM配合使用：

* **CRM MCP查询** — Account Qualification Agent查询实时CRM数据，以便回答和分析反映记录的当前状态。
* **嵌入式插件**—CRM插件在您的CRM中显示[!DNL Marketo Sales Insights] (MSI)分析和代理数据。 使用该插件将潜在客户添加到Marketo Qualifier。
* **活动同步** — 当管理员打开&#x200B;**[!UICONTROL 活动同步]**&#x200B;时，外联活动将同步到CRM和Marketo。

## CRM访问范围

Marketo Qualifier可从CRM中读取用户、联系人、所有者映射、潜在客户、帐户、机会和活动。 它只将记录的外联活动和选择退出状态写入CRM，并将外联活动同步到Marketo。 您的CRM管理员已在Salesforce或Dynamics中准备API访问权限。 然后，Marketo限定符管理员会连接CRM、映射入站字段并选择是否同步活动。

>[!NOTE]
>
>[开始使用](getting-started.md#connect-your-crm)中的凭据步骤描述了对CRM对象的读取权限。 如果您启用了活动同步或选择退出写回，请与您的CRM管理员合作以授予CRM配置所需的相应写访问权限。

## 映射CRM字段（入站映射）

连接CRM后，为连接选择&#x200B;**[!UICONTROL 管理]**&#x200B;并打开&#x200B;**[!UICONTROL 入站映射]**。 入站映射控制Marketo限定符将哪些CRM字段拉入应用程序。

1. 选择&#x200B;**[!UICONTROL 添加节]**。
1. 输入节名称和说明。
1. 选择实体类型。 默认情况下已选择&#x200B;**[!UICONTROL 潜在客户]**。 **[!UICONTROL 联系人]**、**[!UICONTROL 帐户]**&#x200B;和&#x200B;**[!UICONTROL 机会]**&#x200B;也可用。
1. 选择要导入的CRM字段。

   每个字段行显示其&#x200B;**[!UICONTROL 显示名称]**、**[!UICONTROL 字段名称]**&#x200B;和&#x200B;**[!UICONTROL 数据类型]**。

1. 为要作为&#x200B;**[!UICONTROL 潜在客户]**&#x200B;列表中的筛选条件提供的每个潜在客户、联系人或机会字段打开&#x200B;**[!UICONTROL 可筛选]**。
1. 预览该部分并选择&#x200B;**[!UICONTROL 添加]**。

映射的字段显示在Marketo限定符的相应区域中：

* 目标客户字段显示在&#x200B;**[!UICONTROL 人员]**&#x200B;选项卡上。
* 帐户字段显示在&#x200B;**[!UICONTROL 帐户]**&#x200B;选项卡上。
* 机会字段显示在&#x200B;**[!UICONTROL 帐户机会]**&#x200B;部分中。 可过滤的商机字段在&#x200B;**[!UICONTROL 我的商机联系人]**&#x200B;中也会显示为它们自己的列，并带有标签，如&#x200B;**[!UICONTROL 阶段（商机）]**，以便与联系人字段区分开。

## 配置活动同步（出站映射）

1. 从&#x200B;**[!UICONTROL CRM连接]**&#x200B;中，为连接的CRM选择&#x200B;**[!UICONTROL 管理]**。
1. 打开&#x200B;**[!UICONTROL 出站映射]**。
1. 打开&#x200B;**[!UICONTROL 活动同步]**&#x200B;以将Marketo限定符外展活动同步回CRM和Marketo。

关闭活动同步后，Marketo Qualifier将继续使用入站CRM数据，但不会将外联活动与CRM或Marketo同步。

## 配置CRM同步规则

当潜在客户在出站工作流中移动时，Marketo限定符可以自动将潜在客户状态更新写回Salesforce和Microsoft Dynamics，因此代表不再手动更新CRM。

### CRM同步规则的用途

更新可以针对&#x200B;**[!UICONTROL 潜在客户]**、**[!UICONTROL 联系人]**、**[!UICONTROL 帐户]**&#x200B;或&#x200B;**[!UICONTROL 机会]**&#x200B;记录，而不仅仅是潜在客户。

更新将在以下出站工作流时刻触发：

* 已添加到工作流、已回复或已预订的会议
* 由代表删除，或工作流已完成，无回复
* 已选择退出或电子邮件已退回

字段值可以使用动态令牌进行个性化，以便CRM更新反映潜在客户的实际历程而不是静态值。 令牌可用于了解代表姓名、出站工作流名称以及会议日期和时间等详细信息。

只写入与CRM兼容的值，一个失败字段不会阻止其他字段，并且临时问题会自动重试。 每次更新都会进行跟踪，以便您能够查看已同步的内容以及需要注意的内容。

### 设置CRM同步规则

要设置CRM同步规则，请执行以下操作：

1. 在左侧导航中，展开&#x200B;**[!UICONTROL 管理]**，然后选择&#x200B;**[!UICONTROL 管理员设置]** > **[!UICONTROL CRM连接]**。
1. 为连接的CRM选择&#x200B;**[!UICONTROL 管理]**，然后选择&#x200B;**[!UICONTROL 同步规则]**。
1. 选择目标CRM实体和字段，将其映射到上面的工作流时刻，然后打开切换开关。

通过配置CRM同步规则，销售团队可以在每个阶段查看潜在客户、联系人、客户和商机中准确、个性化的最新状态，同时减少数据滞后和手动工作。

## 构建知识中心行动手册 {#knowledge-center}

**[!UICONTROL 知识中心]**&#x200B;允许Account Qualification Agent (AQA)访问您的销售资料。 Marketo Qualifier使用这些材料生成可反映贵组织销售方式的研究、资格鉴定见解和推广活动。 只有管理员才能构建和管理行动手册。

![知识中心](assets/knowledge-center.png){width="800" zoomable="yes"}

1. 在左侧导航中，展开&#x200B;**[!UICONTROL 管理]**，选择&#x200B;**[!UICONTROL 管理员设置]**，然后选择&#x200B;**[!UICONTROL 知识中心]**
1. u
1. 设置Marketo Qualifier用于调查您的公司和草稿电子邮件的&#x200B;**[!UICONTROL 公司名称]**&#x200B;和&#x200B;**[!UICONTROL 公司URL]**。
1. 以PDF、PPTX或DOCX格式上传销售重头戏、理想客户档案(ICP)、定位指南和其他销售宣传资料。
1. 选择&#x200B;**[!UICONTROL 生成行动手册]**。

每个上载的文档都显示其处理状态（如&#x200B;**[!UICONTROL 就绪]**）以及上次更新的时间。

>[!NOTE]
>
>处理行动手册最多需要24小时。

当剧本准备就绪时，代表可以在两个地方使用它：

* **出站电子邮件提示** — 在接触点提示中，命名文档并描述要使用的上下文。 例如，输入`Use the ABC positioning guide from the Knowledge Center and focus on the security value proposition`。 查看[生成和查看接触点](outbound-workflows.md#step-3-generate-and-review-touchpoints)。
* **AI聊天**：请参阅您问题中的知识中心。 例如，输入`From the Knowledge Center, help me position our security solution for ABC Corp before tomorrow's call`。 查看[人工智能聊天](ai-assistant.md)。

在这两种情况下，生成的内容都反映了行动手册中的消息传递，而不是通用研究。

## 配置全局电子邮件选择退出

1. 在左侧导航中，展开&#x200B;**[!UICONTROL 管理]**，然后选择&#x200B;**[!UICONTROL 管理设置]**。
1. 选择&#x200B;**[!UICONTROL 合规性]**&#x200B;下的&#x200B;**[!UICONTROL 电子邮件设置]**。
1. 打开每封电子邮件中的&#x200B;**[!UICONTROL 包含选择退出链接]**&#x200B;以将取消订阅页脚附加到出站电子邮件。
1. 在&#x200B;**[!UICONTROL 选择退出消息模板]**&#x200B;中，输入页脚文本。 在应该显示取消订阅链接的位置包含`{opt_out_link}`令牌。

设置会自动保存。

当目标客户选择链接时，Marketo Qualifier停止向该目标客户发送电子邮件，并将选择退出状态同步到连接的CRM。

## 参考：示例API参数

您的CRM团队可以使用这些示例来确认是否返回预期的潜在客户字段。

### Dynamics OData示例

```text
$select=fullname,_ownerid_value,leadid,emailaddress1,jobtitle,statuscode,createdon,modifiedon,statecode
$filter=_ownerid_value eq '<crmUserId>' [AND additional filters]
$expand=Lead_ActivityPointers(...),parentaccountid(...)
$orderby=modifiedon desc
```

### Salesforce SOQL示例

```sql
SELECT Id, Salutation, FirstName, LastName, Name, Title, Company, Email,
  LeadSource, Status, OwnerId, LastModifiedDate, LastActivityDate, CreatedDate,
  (SELECT Id, Subject, ActivityDate, Status FROM Tasks ORDER BY ActivityDate DESC LIMIT 1),
  (SELECT Id, Subject, ActivityDateTime FROM Events ORDER BY ActivityDateTime DESC LIMIT 1)
FROM Lead
WHERE OwnerId = '<crmUserId>' AND IsDeleted = false
ORDER BY LastModifiedDate DESC
```

>[!MORELIKETHIS]
>
>* [入门](getting-started.md)
>* [潜在客户](prospects.md)

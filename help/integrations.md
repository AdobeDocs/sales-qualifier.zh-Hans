---
title: 管理集成
description: 了解如何在Sales Qualifier中连接Outlook、管理CRM连接、映射入站字段、同步活动和配置全局电子邮件选择退出。
feature: Agentic AI, Sales Insights, Account Journeys
role: User, Admin
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 351b27d35049b0bb576e9b84f7fd6fada791bb52
workflow-type: tm+mt
source-wordcount: 1379
ht-degree: 1%

---


# 集成

连接Outlook以发送电子邮件，识别潜在客户回复，并安排会议。 要使Account Qualification Agent (AQA)和出站工作流能够使用潜在客户、联系人、客户、商机、活动和所有者，您还可以将Sales Qualifier连接到Salesforce或Microsoft Dynamics 365。 Sales Qualifier读取CRM数据，可以将外联活动和选择退出状态写入回CRM，并可以将外联活动同步到Marketo。 它不会修改CRM记录。

本文介绍如何连接Outlook、管理CRM连接、映射字段、同步活动和配置电子邮件选择退出。 若要首次连接CRM，请参阅[开始使用](getting-started.md#connect-your-crm)。

>[!IMPORTANT]
>
>Outlook连接为每个代表。 本文稍后介绍的CRM和合规性设置适用于整个组织。 要访问这些组织范围的设置，您必须属于`Sales Qualifier`和`Sales Qualifier Admins`用户组。 标准用户可以使用配置的CRM数据和过滤器，但无法更改设置。 查看[用户角色和权限](user-roles-permissions.md)。

## 连接Outlook

每个代表都连接自己的Outlook帐户：

1. 选择&#x200B;**[!UICONTROL 连接Outlook]**。
1. 使用您的Microsoft帐户登录。
1. 审阅并批准请求的访问权限。

该连接允许Sales Qualifier从您的邮箱发送、识别潜在客户回复的时间以及在您的日历上安排会议。

连接后，您可以批准允许Sales Qualifier执行以下操作的访问权限：

* 识别来自潜在客户的回复。
* 代表您创建并发送电子邮件。
* 使用您的日历安排会议。
* 读取您的邮箱时区和工作时间以进行计划。
* 保持自动登录状态，以便这些功能可以继续工作，而无需您再次登录。

### Outlook审批（如果需要）

默认情况下，不需要管理员执行任何操作。 每位代表在连接Outlook时自行批准访问权限。

如果贵组织在Microsoft 365或Microsoft Entra中关闭了用户对第三方应用程序的同意，则Microsoft 365或Entra管理员必须针对整个组织批准一次Sales Qualifier。 管理员在代表连接其Outlook帐户之前完成此审批。 在组织范围获得批准后，每个代表都可以连接其帐户。

### Sales Qualifier如何处理您的邮箱数据

Sales Qualifier只读取它发送的电子邮件回复，而不会读取收件箱的其他部分。 它不会将传入附件或电子邮件存储在活动参与之外。 存储的登录凭据将被加密。

## 打开CRM设置

在左侧导航中，展开&#x200B;**[!UICONTROL 管理]**，然后选择&#x200B;**[!UICONTROL 管理设置]**。 这些设置分为两个组：

| 组 | 项目 |
| --- | --- |
| **[!UICONTROL 集成]** | **[!UICONTROL CRM连接]**，**[!UICONTROL 知识中心]** |
| **[!UICONTROL 合规性]** | **[!UICONTROL 电子邮件设置]** |

有关知识中心，请参阅[知识中心](knowledge-center.md)。

## 管理CRM连接

选择&#x200B;**[!UICONTROL CRM连接]**。 该页面包含&#x200B;**[!UICONTROL Salesforce]**&#x200B;和&#x200B;**[!UICONTROL Microsoft]** (Microsoft Dynamics 365)的卡片。 每个信息卡都会显示以下状态之一：

| 状态 | 含义 |
| --- | --- |
| **[!UICONTROL 已连接]** | 连接处于活动状态并已验证。 |
| **[!UICONTROL 非活动]** | 没有为此CRM配置连接。 |
| **[!UICONTROL 所需的权限]** | 连接已验证，但缺少所需的范围。 卡片会列出缺少的范围。 |

>[!NOTE]
>
>一次只能有一个CRM处于活动状态。 当一个CRM连接时，另一个卡被禁用。 在连接其他CRM之前，请断开活动CRM的连接。

未配置的卡片显示&#x200B;**[!UICONTROL 连接]**。 已配置的卡片显示&#x200B;**[!UICONTROL 管理]**&#x200B;和具有&#x200B;**[!UICONTROL 编辑配置]**&#x200B;和&#x200B;**[!UICONTROL 断开连接]**&#x200B;的&#x200B;**[!UICONTROL 更多]**&#x200B;菜单。

### 连接或编辑连接

1. 在CRM卡上，选择&#x200B;**[!UICONTROL 连接]**，或选择&#x200B;**[!UICONTROL 更多]** > **[!UICONTROL 编辑配置]**&#x200B;以更新现有连接。
1. 输入CRM管理员提供的凭据。

   >[!BEGINTABS]

   >[!TAB Salesforce]

   输入&#x200B;**[!UICONTROL 客户端ID（使用者密钥）]**、**[!UICONTROL 实例URL]**&#x200B;和&#x200B;**[!UICONTROL 客户端密钥]**。 使用规范实例URL表单`https://{{mydomain}}.my.salesforce.com`。

   ![Salesforce连接](assets/crm-conn-salesforce.png){width="800" zoomable="yes"}

   >[!TAB Microsoft Dynamics]

   输入&#x200B;**[!UICONTROL 客户端ID（使用者密钥）]**、**[!UICONTROL 租户ID]**、**[!UICONTROL Microsoft Dynamics实例URL]**&#x200B;和&#x200B;**[!UICONTROL 客户端密钥]**。 使用规范实例URL表单`https://{{mydomain}}.crm.dynamics.com`。

   >[!ENDTABS]

1. 选择&#x200B;**[!UICONTROL 连接]**（编辑时选择&#x200B;**[!UICONTROL 保存]**）。

如果Sales Qualifier拒绝凭据，则会确定原因，例如凭据无效或过期、缺少权限或无法识别的Dynamics租户。 请更正该值并重试。

>[!IMPORTANT]
>
>不要通过电子邮件发送客户端密钥。 使用您组织批准的安全渠道与在Sales Qualifier中进入凭据的人共享凭据。

### 断开连接

1. 在连接的CRM卡上，选择&#x200B;**[!UICONTROL 更多]** > **[!UICONTROL 断开连接]**。
1. 查看警告并选择&#x200B;**[!UICONTROL 断开连接]**&#x200B;进行确认。

>[!WARNING]
>
>断开CRM连接后，组织中所有潜在客户的出站工作流都会暂停，并且在您重新连接之前，不会有任何新潜在客户从您的CRM同步。

## 映射CRM字段（入站映射） {#map-crm-fields-inbound-mapping}

入站映射可控制Sales Qualifier导入哪些CRM字段以及这些字段出现的位置。 字段将分组为多个部分，每个部分都属于一种实体类型。

1. 在连接的CRM信息卡上，选择&#x200B;**[!UICONTROL 管理]**。
1. 在&#x200B;**[!UICONTROL 入站映射]**&#x200B;选项卡上，选择&#x200B;**[!UICONTROL 添加节]**。
1. 在&#x200B;**选择节**&#x200B;步骤中，选择实体类型，然后选择&#x200B;**[!UICONTROL 下一步]**：

   | 实体 | 显示其字段的位置 |
   | --- | --- |
   | **[!UICONTROL 潜在客户]** | 目标客户的&#x200B;**[!UICONTROL 人员]**&#x200B;选项卡。 |
   | **[!UICONTROL 联系人]** | 联系人记录。 |
   | **[!UICONTROL 帐户]** | **[!UICONTROL 帐户]**&#x200B;选项卡。 查看[帐户](accounts.md)。 |
   | **[!UICONTROL 商机]** | 客户的机会详细信息。 |

1. 输入&#x200B;**[!UICONTROL 节名称]**&#x200B;和可选的&#x200B;**[!UICONTROL 描述]**。 然后选择&#x200B;**[!UICONTROL 下一步]**。
1. 在&#x200B;**[!UICONTROL 添加字段]**&#x200B;步骤中，搜索并选择要导入的CRM字段。 然后选择&#x200B;**[!UICONTROL 下一步]**。 每个字段显示其&#x200B;**[!UICONTROL 显示名称]**、**[!UICONTROL 字段名称]**&#x200B;和&#x200B;**[!UICONTROL 数据类型]**。
1. 对于&#x200B;**[!UICONTROL 潜在客户]**、**[!UICONTROL 联系人]**&#x200B;和&#x200B;**[!UICONTROL 机会]**&#x200B;分区，为[潜在客户](prospects.md)列表中的代表所需的每个字段启用&#x200B;**[!UICONTROL 可筛选]**。

   如果某个字段的数据类型不支持过滤，或者该字段已用于其他部分，则无法使其可过滤。

   在&#x200B;**[!UICONTROL 我的Opportunity Contacts]**&#x200B;中，可筛选的Opportunity字段显示为单独的列，带有&#x200B;**[!UICONTROL 阶段(Opportunity)]**&#x200B;之类的标签。 后缀可将机会属性与关联联系人上的字段区分开来。

1. 在&#x200B;**[!UICONTROL 预览]**&#x200B;步骤中，确认您的选择并选择&#x200B;**[!UICONTROL 添加]**。

要稍后更改节，请选择节卡片上的&#x200B;**[!UICONTROL 编辑]**。 要删除分区，请在分区卡中选择&#x200B;**[!UICONTROL 删除]**。 要删除单个字段，请在字段行中选择删除操作。 确认每次删除。

## 配置活动同步（出站映射） {#configure-activity-sync-outbound-mapping}

Activity Sync会将Sales Qualifier外联活动写入您的CRM和Marketo。 已发送、已打开、已单击和已回复的电子邮件活动包括出站工作流名称。 代表可以在CRM中查看活动，而营销团队可以在潜在客户评分和参与时间线中使用Marketo活动。

1. 在连接的CRM信息卡上，选择&#x200B;**[!UICONTROL 管理]**。
1. 打开&#x200B;**[!UICONTROL 出站映射]**&#x200B;选项卡。
1. 打开&#x200B;**[!UICONTROL 活动同步]**。 设置将立即保存。

关闭活动同步后，Sales Qualifier将继续使用入站CRM数据，但不会将外联活动与CRM或Marketo同步。

>[!NOTE]
>
>活动同步需要CRM中的写入权限。 如果缺少所需的权限，则会禁用交换机，并且Sales Qualifier会提示您联系管理员。 要授予活动写入权限，请与您的CRM管理员合作。

## 设置营销亮点 {#turn-on-marketo-engagement-filtering}

营销亮点使代表能够按实时[!DNL Marketo]参与度（如电子邮件打开数和点击数）查找潜在客户并确定其优先级。 请参阅[按营销亮点筛选](prospects.md#filter-by-marketing-highlights)。

管理员完成一次性设置，将[!DNL Marketo]连接到相关组织和沙盒的Sales Qualifier。 该设置包括在Adobe Developer Console中创建API凭据，在[!DNL Marketo]中配置webhook，以及将该webhook添加到触发器Smart Campaign。 有关完整步骤，请参阅[设置营销亮点](marketing-highlights-setup.md)。

营销亮点适用于所有生产地区：北美、EMEA和澳大利亚。

## 配置全局电子邮件选择退出 {#configure-global-email-opt-out}

选择退出设置会在每封出站电子邮件后附加取消订阅页脚。 标准用户无法针对单个电子邮件将其关闭。

1. 在左侧导航中，展开&#x200B;**[!UICONTROL 管理]**，然后选择&#x200B;**[!UICONTROL 管理设置]**。
1. 选择&#x200B;**[!UICONTROL 合规性]**&#x200B;下的&#x200B;**[!UICONTROL 电子邮件设置]**。
1. 打开每封电子邮件的&#x200B;**[!UICONTROL 包含选择退出链接]**。
1. 在&#x200B;**[!UICONTROL 选择退出消息模板]**&#x200B;中，输入页脚文本。 包含将显示可点击取消订阅链接的`{opt_out_link}`令牌。

   例如：`If you'd prefer not to receive these emails, you can {opt_out_link}.`

设置和模板会自动保存。

当目标客户选择链接时，Sales Qualifier会停止向该目标客户发送电子邮件，并将选择退出状态同步到连接的CRM。

## CRM访问范围

Sales Qualifier读取它需要的CRM实体，并只回写定义的数据集：

* **读取** — 用户、联系人、所有者映射、潜在客户、客户、商机和活动。
* **写入** — 已记录外展活动（当[活动同步](#configure-activity-sync-outbound-mapping)开启时）和选择退出状态。

您的CRM管理员已在Salesforce或Dynamics中准备API访问权限。 然后，Sales Qualifier管理员会连接CRM、映射入站字段并选择是否同步活动。 初始连接需要只读访问权限。 活动同步和选择退出写回需要相应的写访问权限。

>[!MORELIKETHIS]
>
>* [入门](getting-started.md)
>* [用户角色和权限](user-roles-permissions.md)
>* [帐户](accounts.md)

---
title: Adobe中的潜在客户Marketo限定符
description: 了解如何在Adobe Marketo Qualifier中从CRM、导入和手动添加的来源构建潜在客户列表、筛选潜在客户以及查看潜在客户详细信息。
feature: Agentic AI, Sales Insights, Account Journeys
role: User
TQID: 'https://experienceleague.adobe.com/zf2H5rq1JlIT26LqLPMrm2Mq3tSIrLOiTEw6BXb1w2U'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: CX Enterprise
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
    internal-label: Integrations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: d967b633fcb63c64169d3e3fbf305fd2ff82236d
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 1%
---

# 潜在客户

在左侧导航中选择&#x200B;**[!UICONTROL 潜在客户]**&#x200B;以查看您可以访问的潜在客户和联系人。 使用列表可查看每个潜在客户的状态和最新活动。

![显示潜在客户管理的潜在客户状态和最后一个活动的潜在客户表](./assets/prospects.png){width="800" zoomable="yes"}

* **[!UICONTROL 潜在客户]** — 在连接的CRM中分配给您的潜在客户。
* **[!UICONTROL 联系人]** — 在连接的CRM中分配给您的联系人。
* **[!UICONTROL 营销亮点]** — 具有实时Marketo活动（如电子邮件打开次数或点击次数）的潜在客户。
* **[!UICONTROL 人员列表]** — 您手动导入或添加的潜在客户。

## 构建潜在客户列表

潜在客户列表将来自多个来源的人员组合在一起：

* **CRM潜在客户** — Adobe Marketo限定符会自动导入分配给连接用户的潜在客户和联系人。 查看[集成](integrations.md)。
* **导入的潜在客户** — 从CSV文件导入的潜在客户。
* **手动添加潜在客户** — 单个潜在客户已添加到Marketo限定符中。

要添加不来自您的CRM的潜在客户，请执行以下操作：

1. 在&#x200B;**[!UICONTROL 潜在客户]**&#x200B;页面上，选择&#x200B;**[!UICONTROL 人员列表]**。

   ![人员列表](assets/prospects-people-list.png){width="800" zoomable="yes"}

1. 选择&#x200B;**[!UICONTROL +添加人员]**，然后选择&#x200B;**[!UICONTROL 导入CSV]**&#x200B;或&#x200B;**[!UICONTROL 添加人员]**。

   * 对于CSV导入，请上传`firstname,email`格式的CSV。
     名字和电子邮件为必填项。 姓氏是可选的。 CSV模板不包括CRM商机ID列，但您可以在导入之前将该列及其值添加到文件中。 如果导入失败，请查看错误消息以了解要更正的字段或值，然后再次上传文件。
     映射任何自定义或附加CSV字段，而不仅仅是标准字段。 Marketo限定符会将这些值保存到每个潜在客户中，并在以后提供这些值，包括生成[电子邮件](outbound-workflows.md#step-5-add-prospects-and-start-email-generation)。
   * 要手动添加人员，请在表单中输入其详细信息。

1. 选择&#x200B;**[!UICONTROL 保存]**。

## 筛选和查找潜在客户

选择&#x200B;**[!UICONTROL 筛选器]**&#x200B;以缩小列表范围。 您可以按以下项过滤：

* 出站工作流状态
* 创建者
* 作业名称
* 帐户
* 源
* 上次更新时间

管理员还可以使映射的CRM字段可用作过滤器。 在&#x200B;**[!UICONTROL 管理员设置]**&#x200B;中，为代表用于查找潜在客户的每个字段打开&#x200B;**[!UICONTROL 可筛选]**。 查看[映射CRM字段](integrations.md#map-crm-fields-inbound-mapping)。

在&#x200B;**[!UICONTROL 我的机会联系人]**&#x200B;中，您还可以按联系人关联机会中的字段筛选联系人，如阶段、类型和关闭日期。 机会字段具有标签，例如&#x200B;**[!UICONTROL 阶段（机会）]**，这会将它们与联系人字段区分开来。 您的管理员控制哪些机会字段可用作过滤器。

### 按营销亮点过滤

根据潜在客户的实时[!DNL Marketo]参与情况（如电子邮件打开数和点击数、Web访问数、表单填写数和有趣时刻）查找潜在客户并确定其优先级。 参与几乎实时地出现。

要按营销亮点筛选潜在客户，请执行以下操作：

1. 选择&#x200B;**[!UICONTROL 筛选器]**。
1. 添加营销亮点过滤器并设置活动类型、营销活动或其他属性，以重点关注重要的参与。

每个潜在客户显示其最新的[!DNL Marketo]活动以及最近的历史记录。

营销亮点适用于所有生产区域。 管理员完成一次性设置，将[!DNL Marketo]连接到Marketo限定符。 请参阅[设置营销亮点](integrations.md#turn-on-marketo-engagement-filtering)。

## 查看目标客户详细信息

选择目标客户以打开其配置文件。 在联系您之前，先查看重要的信号：

* **AI人员摘要** — 商机或联系人及其最近参与的AI写入快照。 在回顾各个活动之前，使用摘要了解人员概览。 运行Adobe Journey Optimizer B2B edition Prime或Ultimate的实例上提供了人工智能人员摘要。
* **活动列表** — 按时间顺序排列的活动和最近行为的列表。
* **时间线视图** — 跨渠道参与的可视时间线。
* **已查看内容** — 潜在客户查看的网页和资产。 选择项目以将其打开。

### 生成会议准备

除了现用AI人员摘要之外，您还可以从&#x200B;**[!UICONTROL 会议研究]**&#x200B;选项卡（**[!UICONTROL 帐户研究]**&#x200B;旁边）生成针对特定即将到来的呼叫定制的会议准备。

* **基于目标** — 如果潜在客户注册了正在运行的出站工作流，请选择它。 准备工作将与该叫客工作流的目标保持一致，如预订会议、产品推介、活动邀请或重新吸引潜在客户。
* **自定义提示** — 输入您要准备的内容，例如`Focus on renewal risk`或`Prepare for a technical deep dive with their IT lead`。 准备与您的提示相匹配。 当目标客户不在正在运行的出站工作流中时，自定义提示选项可用。

>[!MORELIKETHIS]
>
>* [帐户](accounts.md)
>* [出站工作流](outbound-workflows.md)
>* [AI聊天](ai-assistant.md)

---
title: Sales Qualifier中的帐户
description: 了解如何在Sales Qualifier中查看客户情报（包括AI研究、最新新闻、机会和主要参与联系人）以优先开展外联。
feature: Agentic AI, Sales Insights, Account Journeys
role: User
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8573d3891d5c8ec8a05637f160f120f933b0ec61
workflow-type: tm+mt
source-wordcount: 632
ht-degree: 0%

---


# 帐户

帐户视图结合了AI生成的研究、最新新闻、开放机会、管道价值和参与联系人。 在联系您之前，请使用此信息了解帐户并排定其优先级。

## 开立帐户

从与其关联的目标客户的配置文件中打开帐户。

1. 在左侧导航中选择&#x200B;**[!UICONTROL 潜在客户]**&#x200B;并打开一个潜在客户。 查看[潜在客户](prospects.md)。
1. 在目标客户详细信息页面上，选择&#x200B;**[!UICONTROL 帐户]**&#x200B;选项卡。

Sales Qualifier从潜在客户的CRM记录中标识帐户。 每个与该帐户关联的目标客户都可以使用相同的帐户视图。 如果Sales Qualifier无法匹配帐户，则选项卡显示&#x200B;_未找到帐户_。

>[!NOTE]
>
>可用的部分和量度取决于您的CRM、贵组织的配置和帐户数据。 如果此处描述的某个部分未显示，则表示未配置所需的数据或功能。

帐户视图有两个选项卡： **[!UICONTROL 详细信息]**&#x200B;和&#x200B;**[!UICONTROL 帐户研究]**。

## 查看帐户详细信息

**[!UICONTROL 详细信息]**&#x200B;选项卡为您提供了帐户及其管道的快照。

### 帐户概述

选项卡顶部的概述卡可识别帐户并汇总其值：

* 帐户名称和区域
* **年度经常性收入(ARR)** — 所有活动订阅的年度经常性收入。 选择&#x200B;**[!UICONTROL 查看全部]**&#x200B;以在&#x200B;**[!UICONTROL 年度经常性收入]**&#x200B;对话框中按产品查看ARR。
* 客户统计，包括未结机会和联系人计数以及管道值

### 帐户概述摘要

**[!UICONTROL 帐户概述]**&#x200B;面板根据CRM数据和Account Qualification Agent研究总结了帐户。 如果正在进行研究，则面板会显示加载状态。 如果无法进行研究，面板会显示一条消息。

### 帐户分析

使用概述下面的按钮可在帐户视图之间切换。 可用的视图取决于您的CRM和配置：

| 视图 | 它显示的内容 |
| --- | --- |
| **[!UICONTROL 商机]** | 打开链接到客户的销售机会，每个销售机会都有键字段。 选择&#x200B;**[!UICONTROL 查看全部]**&#x200B;以查看表中的完整列表。 当管理员使这些字段可过滤时，还可以使用Opportunity详细信息（如阶段、类型和结束日期）在&#x200B;**[!UICONTROL My Opportunity Contacts]**&#x200B;中过滤客户的联系人。 |
| **[!UICONTROL 热门成员]** | 客户参与度最高的联系人，按参与度排名。 每个联系人会显示其职务、电子邮件地址、参与度得分和紧急程度指示器。 |
| **[!UICONTROL 意图数据]** | 为帐户购买意向信号，如帐户正在研究的产品和主题。 |
| **[!UICONTROL 帐户团队成员]** | 分配给帐户的人员，及其电子邮件、职务、地区和产品组。 |
| **[!UICONTROL CRM字段]** | 从您的CRM导入的帐户字段，如集客映射中所配置。 查看[集成](integrations.md#map-crm-fields-inbound-mapping)。 |

从&#x200B;**[!UICONTROL 顶级成员]**&#x200B;视图中，对联系人执行以下任一操作：

* **[!UICONTROL 添加到出站工作流]** — 在[出站工作流](outbound-workflows.md)中注册联系人。
* **[!UICONTROL 添加到Marketo营销活动]** — 触发联系人的[!DNL Marketo]营销活动。

## 研究帐户

**[!UICONTROL 帐户研究]**&#x200B;选项卡包含三个方面：

* **[!UICONTROL 研究类别]** — 研究主题。 选择一个类别，以在中心窗格中查看其研究。
* **研究内容** — 按类别分组的AI生成的研究卡。 卡片可包含源域以及首次和上次检测到信号的日期。
* **[!UICONTROL 最新新闻]** — 有关帐户的最新新闻，包括日期、标记和源链接。

如果无法加载研究或新闻，则每个区域都提供&#x200B;**[!UICONTROL 重新加载]**&#x200B;操作以重试。

## 在外联中使用客户情报

帐户智能在决定您发送的内容时最有价值：

* 参考最近的新闻项目或研究信号，使您的开场变得相关，而不是使用通用的推介。
* 检查未结机会和管道值以确定是否划分帐户的优先级。
* 使用&#x200B;**[!UICONTROL 顶级成员]**&#x200B;确定联系对象，然后将其注册到出站工作流。
* 在呼叫之前询问[AI聊天](ai-assistant.md)以开发帐户的定位。

>[!MORELIKETHIS]
>
>* [潜在客户](prospects.md)
>* [出站工作流](outbound-workflows.md)
>* [AI聊天](ai-assistant.md)

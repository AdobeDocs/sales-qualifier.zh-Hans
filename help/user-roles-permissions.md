---
title: 用户角色和权限
description: 了解Sales Qualifier用户组如何控制应用程序和管理访问权限。
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
TQID: 'https://experienceleague.adobe.com/9X9DYGMvLGcPG--G6rHcDEk91hdT9-XYc9wbiL2Qoww'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8573d3891d5c8ec8a05637f160f120f933b0ec61
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 4%

---


# 用户角色和权限

Sales Qualifier使用两个必需的用户组将销售任务与组织范围的配置分开。

## 必需的用户组

| 组 | 谁属于 | 授予的内容 |
| --- | --- | --- |
| `Sales Qualifier` | 每个用户，包括管理员 | 对应用程序的访问权限：潜在客户、帐户、出站工作流、任务、性能和用户档案设置。 |
| `Sales Qualifier Admins` | 除了`Sales Qualifier`组之外，仅限管理员 | 访问&#x200B;**[!UICONTROL 管理员设置]**，它管理整个组织的CRM连接、知识中心和合规性设置。 |

标准用户只需要`Sales Qualifier`组。 管理员需要两个组中的成员资格。 请参阅[开始使用](getting-started.md)以创建这些组。

组织还可以创建可选的`Sales Qualifier BDR managers`组。 成员可以访问电子邮件性能报表。

## 管理员访问权限

**[!UICONTROL 管理员设置]**&#x200B;仅显示在&#x200B;**[!UICONTROL 管理]**&#x200B;下，适用于同时属于两个所需组的用户。 对这些设置所做的更改适用于整个组织。

## 管理员控制

| 设置 | 在何处配置它 | 效果 |
| --- | --- | --- |
| CRM连接和字段映射 | [集成](integrations.md#map-crm-fields-inbound-mapping) | 确定目标客户或帐户显示的CRM字段以及可用作筛选器的字段。 |
| 全局电子邮件选择退出 | [集成](integrations.md#configure-global-email-opt-out) | 向每封出站电子邮件添加取消订阅页脚。 |
| 知识中心和行动手册 | [知识中心](knowledge-center.md) | 使公司行动手册在出站提示和[AI聊天](ai-assistant.md)中可用。 |
| 活动同步 | [集成](integrations.md#configure-activity-sync-outbound-mapping) | 确定Sales Qualifier外联活动是否显示在CRM中。 |

标准用户可以使用这些设置，但无法更改它们。 如果缺少预期的过滤器、行动手册引用或CRM字段，请联系管理员。

>[!MORELIKETHIS]
>
>* [入门](getting-started.md)
>* [集成](integrations.md)
>* [知识中心](knowledge-center.md)

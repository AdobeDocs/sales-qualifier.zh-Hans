---
title: Sales Qualifier中的任务
description: 了解如何在Sales Qualifier任务队列中处理手动外联任务并审查代理建议的潜在客户。
feature: Agentic AI, Sales Insights, Account Journeys
role: User
TQID: 'https://experienceleague.adobe.com/MbTN1r-ARrW-XYtdIS-KZT7K1Lk-B3GihT8iXL60GrQ'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8573d3891d5c8ec8a05637f160f120f933b0ec61
workflow-type: tm+mt
source-wordcount: 900
ht-degree: 0%

---


# 任务

使用&#x200B;**[!UICONTROL 任务]**&#x200B;完成出站工作流生成的操作。 选择任务，执行操作，将任务标记为“完成”，然后在不离开页面的情况下继续执行下一个任务。

在左侧导航中，转到&#x200B;**[!UICONTROL 活动]** > **[!UICONTROL 任务]**。

## 任务视图

该页面有两个选项卡：

* **[!UICONTROL 手动任务]** — 已注册出站工作流的潜在客户的电话呼叫、LinkedIn InMails和电子邮件审核。
* **[!UICONTROL 代理建议]** — 符合出站工作流的定位条件并且建议注册的潜在客户。

每个选项卡都有自己的过滤器、排序选项和双面板布局。 任务列表显示在左侧，工作面板显示在右侧。 选择任务会在工作面板中加载其详细信息。 当您完成任务时，将自动选择下一个任务。

## 手动任务

### 任务类型

手动任务与叫客工作流步骤相关联，并有三种类型：

* **[!UICONTROL 电话呼叫]** — 在节奏到达电话呼叫步骤时创建。 工作面板显示潜在客户的电话号码和AI生成的呼叫脚本（如果可用）。

* **[!UICONTROL LinkedIn InMail]** — 在节奏到达LinkedIn InMail步骤时创建。 工作面板显示要从LinkedIn复制和发送的内容。 展开&#x200B;**[!UICONTROL AI理由]**&#x200B;以查看理由。

* **[!UICONTROL 电子邮件审核]** — 在Sales Qualifier生成潜在客户的个性化电子邮件之后创建。 选择&#x200B;**[!UICONTROL 审阅电子邮件]**&#x200B;以在开始外展之前审阅和批准草稿。 查看[查看和优化生成的电子邮件](outbound-workflows.md#review-and-refine-generated-emails)。

### 工作面板

对于&#x200B;**[!UICONTROL 电话呼叫]**&#x200B;或&#x200B;**[!UICONTROL LinkedIn InMail]**&#x200B;任务，工作面板包含：

* **[!UICONTROL 潜在客户]** — 潜在客户的姓名、电子邮件链接和电话号码（如果适用）。
* **[!UICONTROL 出站工作流]** — 链接的出站工作流名称、截止日期和自动跳过指示器（如果适用）。
* **任务内容** — 调用脚本或InMail内容。
* **[!UICONTROL 注释]** — 选择其他任务时会自动保存注释。 完成、跳过或取消任务后无法编辑注释。

### 生成调用脚本

对于&#x200B;**[!UICONTROL 电话呼叫]**&#x200B;任务，请选择&#x200B;**[!UICONTROL 生成呼叫脚本]**。 生成完成后，选择&#x200B;**[!UICONTROL 查看详细的调用脚本]**。 如果生成失败，请从面板重试。

### 任务操作

工作面板标题中有两个操作可用：

* **[!UICONTROL 标记完成]** — 请在发出呼叫、发送InMail或查看电子邮件后执行此操作。 队列前进到下一个任务。
* **[!UICONTROL 跳过]** — 当您无法完成此步骤但希望将潜在客户保留在出站工作流中时，请使用此操作。 前景进入下一个步调。

如果呼叫和LinkedInMail任务在配置的阈值后仍未完成，则可以自动跳过这些任务。 自动跳过会加快潜在客户的发展速度，不会影响计划的电子邮件接触点。

### 筛选、搜索和排序

列表上方的工具栏控制显示哪些任务以及按什么顺序。 您的筛选器和排序选择将保存并在下次打开页面时重新应用。

* **[!UICONTROL 筛选器]** — 打开筛选器面板：
  * **[!UICONTROL 状态]**—**[!UICONTROL 当前]**，**[!UICONTROL 即将到来]**，**[!UICONTROL 过期]**，**[!UICONTROL 已完成]**，**[!UICONTROL 已取消]**，**[!UICONTROL 已跳过]**。
  * **[!UICONTROL 任务类型]**—**[!UICONTROL 电子邮件审核]**，**[!UICONTROL LinkedIn InMail]**，**[!UICONTROL 电话]**。
  * **[!UICONTROL 到期日期]**。
  * **[!UICONTROL 出站工作流]** — 出站工作流的可搜索列表。
* **[!UICONTROL 排序]** — 按到期日期或创建日期排序。 排序顺序还决定了队列前进的顺序。
* **[!UICONTROL 搜索任务]** — 按潜在客户名称、公司名称或出站工作流查找任务。 搜索适用于活动的过滤器。

活动过滤器在工具栏下方显示为切片。 选择&#x200B;**[!UICONTROL 全部清除]**&#x200B;以重置它们。

### 任务状态

每个任务都会显示其当前状态：

| 状态 | 描述 |
| --- | --- |
| **[!UICONTROL 当前]** | 现在截止并准备采取行动。 当前任务不显示徽章。 |
| **[!UICONTROL 即将推出]** | 上一步已完成，但到期日期是将来的日期。 如果时机正确，你可以早点行动。 |
| **[!UICONTROL 过期]** | 已超过到期日期，但尚未完成。 已标记任务以引起注意。 |
| **[!UICONTROL 已完成]** | 您已完成操作并将任务标记为“完成”。 |
| **[!UICONTROL 跳过]** | 您已跳过该步骤，或该步骤已自动跳过。 潜在客户在出站工作流中前进。 |
| **[!UICONTROL 已取消]** | 由于出站工作流更改，系统取消了任务。 |

已完成、已跳过和已取消的任务是最终任务。 他们的操作不再可用，并且其注释为只读。

## 代理建议

**[!UICONTROL 代理建议]**&#x200B;选项卡列出了与出站工作流的定位条件匹配且建议注册的潜在客户。 要启用推荐，请参阅[出站工作流](outbound-workflows.md)。

选择建议以在工作面板中对其进行审阅：

* 回访间隔徽章将每个建议标记为&#x200B;**[!UICONTROL 新]**&#x200B;或&#x200B;**[!UICONTROL 上一个]**。
* **[!UICONTROL 推荐的潜在客户]**&#x200B;或&#x200B;**[!UICONTROL 推荐联系人]**&#x200B;表列出了推荐的潜在客户，其中包含&#x200B;**[!UICONTROL 姓名]**、**[!UICONTROL 标题]**、**[!UICONTROL 帐户]**、**[!UICONTROL 状态]**、**[!UICONTROL 电子邮件]**&#x200B;和&#x200B;**[!UICONTROL 上次更新时间]**&#x200B;的列。

有两个操作可用：

* **[!UICONTROL 审核潜在客户]** — 打开出站工作流以审核和注册推荐的潜在客户。 查看[添加潜在客户并开始生成电子邮件](outbound-workflows.md#step-5-add-prospects-and-start-email-generation)。
* **[!UICONTROL 标记为完成]** — 审阅建议后将其关闭。

**[!UICONTROL 代理建议]**&#x200B;选项卡包括&#x200B;**[!UICONTROL 当前]**、**[!UICONTROL 已完成]**&#x200B;和&#x200B;**[!UICONTROL 已取消]**&#x200B;状态筛选器、出站工作流筛选器以及按创建日期排序。

## 从出站工作流完成任务

在出站工作流的&#x200B;**[!UICONTROL 参与的潜在客户]**&#x200B;视图中，手动接触点提供了相同的&#x200B;**[!UICONTROL 标记为完成]**、**[!UICONTROL 跳过]**&#x200B;和注释选项。 在该处完成任务也会在&#x200B;**[!UICONTROL 任务]**&#x200B;页面上更新其状态。 请参阅[出站工作流](outbound-workflows.md)。

## 空状态

* 当没有任务要执行时，列表显示&#x200B;_您今天已全部完成_&#x200B;消息。
* 当过滤器与任何任务都不匹配时，列表报告没有任务与您的过滤器匹配。
* 如果未选择任务，则工作面板会提示您选择任务以查看其详细信息。

>[!MORELIKETHIS]
>
>* [出站工作流](outbound-workflows.md)
>* [出站性能](performance.md)
>* [潜在客户](prospects.md)

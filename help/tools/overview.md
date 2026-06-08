---
title: 代理工具
description: 比較Builders的MCP伺服器、代理程式技能和API，並為Adobe CX Enterprise工作流程選擇正確的代理程式工具。
index: false
source-git-commit: 63f5958eaa227ea21fa5b193a2ac76a69fd349cb
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 1%

---


# 代理工具

<!-- last-modified: 2026-05-08 -->

並非所有仿造工具方法都有相同的需求。 MCP伺服器可讓您從任何相容的AI使用者端以自然語言立即存取Adobe資料，而不需要編碼。 代理程式技能會將Adobe網域專業知識編碼為可重複的代理程式工作流程，以便每次都能一致地執行任務。 API可讓開發人員完全以程式設計方式控制建置自訂應用程式和整合。 本頁說明權衡，讓您選擇適合自己情況的正確起點。

<!--
CARDS

* mcp-servers.md
  {title = MCP Servers}
  {description = Connect any compatible AI client to Adobe CX Enterprise data and workflows. No coding required.}
  {cta = Explore MCP Servers}
  {image = ../assets/mcp-servers-card.png}

* agent-skills.md
  {title = Agent Skills}
  {description = Adobe-curated workflow instructions that guide agents through CX Enterprise tasks consistently.}
  {cta = Explore Agent Skills}
  {image = ../assets/agent-skills-card.png}

* apis.md
  {title = APIs for Builders}
  {description = Build custom applications and integrations using the same APIs that power Adobe products.}
  {cta = Explore APIs for Builders}
  {image = ../assets/apis-card.png}

-->

## 比較代理工具

| | MCP伺服器 | 代理程式技能 | 適用於建置器的API |
| --- | --- | --- | --- |
| 最適合 | AI使用者端使用者 | 所有使用者 | 開發人員 |
| 需要編碼 | 無 | 無 | 是 |
| 設定時間 | 分鐘 | 分鐘 | 小時到天 |
| 您的收穫 | 從您的AI工具存取Adobe | 引導式、可重複的工作流程 | 完整的程式化控制 |
| 需要AI使用者端 | 是 | 是 | 選填 |

## 不確定從何處開始？

- 若要使用AI與Adobe CX Enterprise應用程式互動（執行動作、查詢資料，以及讓AI透過自然對話探索後續動作），[MCP伺服器](mcp-servers.md)是最靈活的起點。
- 若要讓代理程式持續遵循Adobe原生工作流程，而不需要即興發揮，[代理程式技能](agent-skills.md)會以可重複使用的指示對網域專業知識進行編碼。
- 若要建置可簡化或自動化使用者特定Adobe工作流程的重點應用程式，[建置器適用的API](apis.md)可讓您直接、可程式化地控制即將發生的事情。

>[!BEGINTABS]

>[!TAB MCP伺服器]

將MCP伺服器視為您的AI工具和Adobe之間的即時連線。 連線一次，您的AI就可以查詢行銷活動、提取對象、檢查歷程狀態等。 全部都使用純語言，不需要程式碼。

**使用MCP伺服器時：**

- 您希望Adobe資料位於已使用的AI工具中
- 您正在執行探索性分析或臨時資料擷取
- 您想要快速獲得結果，而不需要旋轉專案

**試用：**&#x200B;請要求Claude總結您使用中的歷程。 從ChatGPT提取Real-Time CDP對象大小。 檢閱CJA促銷活動量度，而不開啟控制面板。

[探索MCP伺服器](mcp-servers.md)

>[!TAB 代理程式技能]

代理商技能是Adobe的網域專業知識，會編碼為您的代理商可遵循的指示。 與其希望您的代理程式找出正確的步驟，不如用技能告訴它該做什麼。 可靠、可重複，並且已針對Adobe工作流程進行調整。

**使用代理程式技能時間：**

- 您想要每次都以相同的方式完成相同的工作
- 您正在執行可重複的內容或媒體製作工作流程
- 您想要一個知道Adobe的代理，而不需要您說明

**試試看：**&#x200B;批次編輯一組像片以看起來有凝聚力。 從單一來源資產產生可適用於平台的社交變體。 在幾個提示中從Adobe Express範本進行設計。

[探索代理程式技能](agent-skills.md)

>建置器的[!TAB API]

API是建置區塊。 它們可讓開發人員透過支援Adobe產品的API，以程式設計方式直接存取Adobe資料和作業。 使用它們來建置一些按照您的排程、條款和棧疊執行的專案。

**使用API時間：**

- 您正在建置自訂應用程式或儀表板
- 您需要將Adobe資料整合到另一個系統中
- 您正在使用Claude程式碼或游標產生完整的應用程式
- 您需要完整建立、更新或刪除控制項

**試用：**&#x200B;建置自訂行銷活動儀表板。 自動化資料管道。 使用Claude程式碼產生可讀取和寫入Adobe Experience Platform的應用程式。

[探索建置器的API](apis.md)

>[!ENDTABS]

## 搭配使用

MCP伺服器、代理程式技能和API是互補的。 許多工作流程會結合這三項：

- 代理程式技能會定義工作流程並指引代理程式
- MCP伺服器可讓代理程式在工作流程中讀取Adobe資料
- API可處理需要直接系統寫入或自訂應用程式邏輯的動作

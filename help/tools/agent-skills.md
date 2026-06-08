---
title: 代理程式技能
description: 由Adobe組織的工作流程與指示，可引導AI代理一致地完成CX Enterprise工作。
index: false
source-git-commit: 63f5958eaa227ea21fa5b193a2ac76a69fd349cb
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 2%

---


# 代理程式技能

<!-- last-modified: 2026-05-19 -->

Adobe CX Enterprise的![代理程式技能](../assets/hero-agent-skills.png)

代理程式技能是Adobe組織的工作流程，可為AI代理程式提供逐步指示，以便可靠地完成Adobe CX Enterprise工作。 每個「代理程式技能」都會編碼領域專業知識與最佳實務，如此代理程式便能產生一致、驗證的結果，而不需要即興發揮。 如果您想要跨對話進行可重複的引導式行為，尤其是針對每次都需要詳細提示的工作，「代理程式技能」才有意義。 它們補充了MCP伺服器和API：代理程式技能定義代理程式的運作方式；MCP伺服器和API提供基礎存取。

所有代理程式技能都保留在[Adobe Skills GitHub存放庫](https://github.com/adobe/skills)中，這是代理程式技能檔案、安裝和實施詳細資訊的主要來源。

## Adobe CX Enterprise Agent技能

所有代理程式技能都會保留在[Adobe Skills GitHub存放庫](https://github.com/adobe/skills)。 選取下方的功能區域以探索該工作流程的技能。

### Adobe應用程式

<!--
CARDS

* https://github.com/adobe/skills/tree/main/plugins/aem
  {title = Adobe Experience Manager}
  {description = Agent Skills for Experience Manager development, content, design, and project management across AEM as a Cloud Service, Edge Delivery Services, and AEM 6.5 LTS.}
  {cta = View Agent Skills}
  {target = _blank}
  {image = ../assets/agent-skills-aem-card.png}

* https://github.com/adobe/skills/tree/main/plugins/adobe-analytics
  {title = Adobe Analytics}
  {description = Agent Skills for KPI monitoring, funnel analysis, and executive reporting workflows in Adobe Analytics.}
  {cta = View Agent Skills}
  {target = _blank}
  {image = ../assets/agent-skills-analytics-card.png}

* https://github.com/adobe/skills/tree/main/plugins/adobe-cja
  {title = Customer Journey Analytics}
  {description = Agent Skills for performance comparison, dimension analysis, and workspace authoring in Customer Journey Analytics.}
  {cta = View Agent Skills}
  {target = _blank}
  {image = ../assets/agent-skills-cja-card.png}

* https://github.com/adobe/skills/tree/main/plugins/app-builder
  {title = Adobe App Builder}
  {description = Agent Skills for scaffolding, testing, and deploying custom applications with Adobe App Builder.}
  {cta = View Agent Skills}
  {target = _blank}
  {image = ../assets/agent-skills-cxenterprise-card.png}

* https://github.com/adobe/skills/tree/main/plugins/creative-cloud
  {title = Creative Cloud}
  {description = Agent Skills for batch photo editing, design from templates, video editing, and social media variants with Creative Cloud.}
  {cta = View Agent Skills}
  {target = _blank}
  {image = ../assets/agent-skills-creative-cloud.png}

-->

如需完整的技能詳細資料、安裝方法和原始程式碼，請參閱[Adobe Skills GitHub存放庫](https://github.com/adobe/skills)。

## 代理程式技能如何運作

![代理程式技能如何運作](../assets/hero-connect-agent-skills.gif)

代理程式技能是告訴AI代理程式如何使用Adobe代理程式工具完成任務的一組指示。 代理程式載入技能時，會依照該工作流程進行，而非即興發揮。

- 代理程式每次都以相同的方式完成工作
- 網域專業知識經過一次編碼，並在所有交談中重複使用
- 技能可將多個代理工具和動作鏈結到單一工作流程中

## 開始使用

代理程式技能會根據您使用的AI使用者端進行安裝。 有些使用者端支援從命令列直接安裝：

- **克勞德程式碼**： `/plugin install adobe/skills`
- **節點環境**： `npx skills add adobe/skills`
- **GitHub CLI**： `gh upskill adobe/skills`

其他使用者端會要求您將技能檔案直接下載並新增至您的AI使用者端。 如需使用者端的完整安裝指示，請參閱GitHub](https://github.com/adobe/skills#installation)上的[Adobe技能讀我檔案。

### 尋找代理程式技能

瀏覽[Adobe Skills GitHub存放庫](https://github.com/adobe/skills)中可用技能的完整清單。 每個代理程式技能都包含一個`SKILL.md`檔案，其中包含詳細的指引、參考資料和範例。

在安裝或新增`adobe/skills`套件後，有些AI使用者端可讓您直接列出所有可用的技能：

- **克勞德程式碼**： `claude /plugin list`
- **節點環境**： `npx skills list`
- **GitHub CLI**： `gh upskill list`

## 代理程式技能vs MCP伺服器vs API for Builders

| | 代理程式技能 | MCP伺服器 | 適用於建置器的API |
| --- | --- | --- | --- |
| 目的 | 引導式工作流程和最佳實務 | Adobe資料和工作流程存取 | 直接系統整合 |
| 編碼網域專業知識 | 是 | 無 | 無 |
| 需要編碼 | 無 | 無 | 是 |
| 最適合 | 可重複、引導式工作 | 資料查詢和工作流程動作 | 自訂應用程式開發 |

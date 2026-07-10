---
title: 代理程式技能
description: 由Adobe組織的工作流程與指示，可引導AI代理一致地完成CX Enterprise工作。
last-substantial-update: 2026-05-19T00:00:00Z
source-git-commit: 40d93f878ba9f48c9daffd3beccb4bf829113a36
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 1%

---


# 代理程式技能

<!-- last-modified: 2026-06-11 -->

Adobe CX Enterprise的![代理程式技能](../assets/hero-agent-skills.png)

代理程式技能是Adobe組織的工作流程，可為AI代理程式提供逐步指示，以便可靠地完成Adobe CX Enterprise工作。 每個「代理程式技能」都會編碼領域專業知識與最佳實務，如此代理程式便能產生一致、驗證的結果，而不需要即興發揮。 如果您想要跨對話進行可重複的引導式行為，尤其是針對每次都需要詳細提示的工作，「代理程式技能」才有意義。 它們補充了MCP伺服器和API：代理程式技能定義代理程式的運作方式；MCP伺服器和API提供基礎存取。

## Adobe CX Enterprise代理程式技能

選取下方的功能區域以探索該工作流程的技能。

>[!BEGINTABS]

>[!TAB Adobe Experience Manager]

適用於AEM as a Cloud Service、Edge Delivery Services和AEM 6.5 LTS的Experience Manager開發、內容、設計和專案管理的代理程式技能。

[檢視代理程式技能](https://github.com/adobe/skills/tree/main/plugins/aem)

>[!TAB Adobe Analytics]

Adobe Analytics中KPI監控、funnel分析和執行報告工作流程的代理程式技能。

[檢視代理程式技能](https://github.com/adobe/skills/tree/main/plugins/adobe-analytics)

>[!TAB Customer Journey Analytics]

在Customer Journey Analytics中進行效能比較、維度分析以及工作區編寫的代理程式技能。

[檢視代理程式技能](https://github.com/adobe/skills/tree/main/plugins/adobe-cja)

>[!TAB Adobe App Builder]

使用Adobe App Builder搭配、測試和部署自訂應用程式的代理程式技能。

[檢視代理程式技能](https://github.com/adobe/skills/tree/main/plugins/app-builder)

>[!TAB Creative Cloud]

使用Creative Cloud批次編輯像片、使用範本設計、編輯視訊和社群媒體變體的代理程式技能。

[檢視代理程式技能](https://github.com/adobe/skills/tree/main/plugins/creative-cloud)

>[!ENDTABS]

## 新增代理程式技能

![代理程式技能如何運作](../assets/hero-connect-agent-skills.gif)

代理程式技能是告訴AI代理程式如何使用Adobe代理程式工具完成任務的一組指示。 代理程式載入技能時，會依照該工作流程進行，而非即興發揮。

### 安裝代理程式技能

代理程式技能會根據您使用的AI使用者端進行安裝。 有些使用者端支援從命令列直接安裝：

- **克勞德程式碼**： `/plugin install adobe/skills`
- **節點環境**： `npx skills add adobe/skills`
- **GitHub CLI**： `gh upskill adobe/skills`

其他使用者端會要求您將技能檔案直接下載並新增至您的AI使用者端。 如需使用者端的完整安裝指示，請參閱GitHub[&#128279;](https://github.com/adobe/skills#installation)上的Adobe技能讀我檔案。

### 尋找代理程式技能

瀏覽[Adobe Skills GitHub存放庫](https://github.com/adobe/skills)中可用技能的完整清單。 每個代理程式技能都包含一個`SKILL.md`檔案，其中包含詳細的指引、參考資料和範例。

在安裝或新增`adobe/skills`套件後，有些AI使用者端可讓您直接列出所有可用的技能：

- **克勞德程式碼**： `claude /plugin list`
- **節點環境**： `npx skills list`
- **GitHub CLI**： `gh upskill list`

## 代理程式實際操作技能

代理程式技能可讓Adobe網域專長在您的AI使用者端中運作，因此代理程式會遵循證實的工作流程，而非即興發揮。 以下每個逐步解說都會顯示以可靠方式完成的特定業務任務，並以Adobe最佳實務為指引，從開始到結束全程執行。

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/ai/ai-assisted-development/use-cases/component-development
  {title = Develop AEM components with AI}
  {description = Use Claude Code or Cursor with Agent Skills to scaffold, code, and refine AEM components guided by Adobe best practices.}
  {cta = Try with Agent Skills}
  {image = ../assets/agent-skills-card.png}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Develop AEM components with AI">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/ai/ai-assisted-development/use-cases/component-development" title="使用AI開發AEM元件" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../assets/agent-skills-card.png" alt="使用AI開發AEM元件"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/ai/ai-assisted-development/use-cases/component-development" target="_blank" rel="referrer" title="使用AI開發AEM元件">使用AI開發AEM元件</a>
                    </p>
                    <p class="is-size-6">使用具備代理程式技能的Claude程式碼或Cursor ，在Adobe最佳實務的指引下，搭配、編碼和調整AEM元件。</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/ai/ai-assisted-development/use-cases/component-development" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">嘗試使用代理程式技能</span>
                
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

---
title: 代理工具
description: 比較MCP伺服器、代理程式技能以及適用於建置器的API，並為Adobe CX Enterprise工作流程選擇正確的代理程式工具。
last-substantial-update: 2026-11-16
source-git-commit: a75d5f3af3077b259da796bd381d605ae826585d
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 1%
---

# 代理式工具

<!-- last-modified: 2026-06-08 -->

並非每個代理程式工具都有相同的需求。 探索每個專案的功能、使用時間以及如何開始，以便您針對自己的情況選擇正確的起點。

<!--
CARDS

* mcp-servers.md
  {title = MCP Servers}
  {description = Connect any compatible AI platform to Adobe CX Enterprise data and workflows. No coding required.}
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
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="MCP Servers">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="mcp-servers.md" title="MCP 伺服器">
                        <img class="is-bordered-r-small" src="../assets/mcp-servers-card.png" alt="MCP 伺服器"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="mcp-servers.md" title="MCP 伺服器">MCP伺服器</a>
                    </p>
                    <p class="is-size-6">將任何相容的AI平台連線到Adobe CX Enterprise資料和工作流程。 不需要編碼。</p>
                </div>
                <a href="mcp-servers.md" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">探索MCP伺服器</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Agent Skills">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="agent-skills.md" title="代理程式技能">
                        <img class="is-bordered-r-small" src="../assets/agent-skills-card.png" alt="代理程式技能"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="agent-skills.md" title="代理程式技能">代理程式技能</a>
                    </p>
                    <p class="is-size-6">由Adobe組織的工作流程指示，可引導代理一致地完成CX Enterprise工作。</p>
                </div>
                <a href="agent-skills.md" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">探索代理程式技能</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="APIs for Builders">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="apis.md" title="適用於建置器的API">
                        <img class="is-bordered-r-small" src="../assets/apis-card.png" alt="適用於建置器的API"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        建置器的<a href="apis.md" title="適用於建置器的API">API</a>
                    </p>
                    <p class="is-size-6">使用支援Adobe產品的相同API來建立自訂應用程式和整合。</p>
                </div>
                <a href="apis.md" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">探索建置器的API</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->


## 比較代理工具

| | MCP 伺服器 | 代理程式技能 | 適用於建置器的API |
| --- | --- | --- | --- |
| 最適合 | CX Enterprise應用程式使用者 | CX Enterprise應用程式使用者和開發人員 | 開發人員 |
| 需要編碼 | 無 | 無 | 是 |
| 設定時間 | 分鐘 | 分鐘 | 小時到天 |
| 您的收穫 | 從您的AI平台存取CX Enterprise應用程式 | 引導式、可重複的工作流程 | 完整的程式化控制 |

## 不確定從何處開始？

- 若要使用AI與CX Enterprise應用程式互動（執行動作、查詢資料，以及讓AI透過自然對話來探索後續動作），[MCP伺服器](mcp-servers.md)是最靈活的起點。
- 若要讓代理程式持續遵循CX Enterprise工作流程的Adobe最佳實務，而不需要即興發揮，[代理程式技能](agent-skills.md)會在可重複使用的指示中編碼該網域專業知識。
- 若要建置可簡化或自動化使用者特定CX Enterprise工作流程的重點應用程式，[建置器適用的API](apis.md)可讓您直接、可程式化地控制即將發生的事情。

>[!BEGINTABS]

>[!TAB MCP伺服器]

將MCP伺服器視為您AI平台和CX Enterprise應用程式之間的即時連線。 從[適用於AI平台的Adobe CX Enterprise Coworker](mcp-servers.md#connect-to-your-ai-platform)開始：連線一次，您的AI平台就可以使用Adobe CX Enterprise Coworker來查詢行銷活動、拉取對象、檢查歷程狀態等等，這一切都以純文字表示，不需要任何程式碼。 如果它不適合您，請直接連線到[產品MCP伺服器](mcp-servers.md#connect-to-your-ai-platform)。

**使用MCP伺服器時：**

- 您想要將AI直接整合至CX Enterprise工作流程
- 您希望CX Enterprise資料位於已使用的AI平台中
- 您正在執行探索性分析或臨時資料擷取
- 您想要快速獲得結果，而不需要旋轉專案

[探索MCP伺服器](mcp-servers.md)

>[!TAB 代理程式技能]

代理商技能是Adobe的網域專業知識，會編碼為您的代理商可遵循的指示。 技能不會希望您的代理程式找出正確的步驟，而是會明確告知您應該做什麼、可靠、可重複，並且已針對CX Enterprise工作流程進行調整。

**使用代理程式技能時間：**

- 透過AI平台在Adobe應用程式中執行工作時，您想要遵循CX Enterprise最佳實務
- 您想要每次都以相同的方式完成相同的工作
- 您正在執行可重複的內容或媒體製作工作流程

[探索代理程式技能](agent-skills.md)

>[!TAB 建置器的 API]

API是建置區塊。 它們可讓開發人員透過支援Adobe產品的API，以程式設計方式直接存取Adobe資料和作業。 運用這些工具，建置重點明確的自訂體驗，透過組織需求的護欄，簡化特定業務工作流程。

**使用API時間：**

- 您正在建置特定業務使用案例的自訂應用程式或整合
- 您需要使用特定護欄和控制項最佳化或自動化工作流程
- 您正在使用Claude程式碼或游標產生完整的應用程式
- 您需要將CX Enterprise資料整合到另一個系統中

[探索建置器的API](apis.md)

>[!ENDTABS]

## 搭配使用

這些工具的設計目的是搭配使用。 結合這兩個功能，您就能充分利用Adobe AI。 代理程式技能可以指導AI平台如何使用MCP伺服器，讓代理程式在CX Enterprise工作流程中保持正確的軌跡。 技能也可以告知呼叫API的方法和時機，將Adobe最佳實務護欄新增到自訂自動化。 您不必只選擇一個。

## 執行中的代理工具

檢視這些套用至實際CX Enterprise工作流程的工具。

<!--
CARDS

* ../use-cases/query-audiences.md
  {title = Audience activation at a glance}
  {description = See which audiences are live, where they are flowing, and whether destinations are healthy, without navigating Real-Time CDP.}
  {cta = Check audience activation}

* https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/ai/ai-assisted-development/use-cases/component-development
  {title = Develop AEM components with AI}
  {description = Use Claude Code or Cursor with Agent Skills to scaffold, code, and refine AEM components guided by Adobe best practices.}
  {cta = Try with Agent Skills}
  {image = ../assets/agent-skills-card.png}

* https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/aem-apis/openapis/invoke-api-using-oauth-web-app
  {title = Invoke AEM APIs from a web app}
  {description = Build a web application that authenticates users and calls AEM OpenAPIs using OAuth to deliver governed, programmatic access.}
  {cta = Try with APIs}
  {image = ../assets/using-api-card.png}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Audience activation at a glance">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="../use-cases/query-audiences.md" title="對象啟用總覽">
                        <img class="is-bordered-r-small" src="../assets/use-cases/query-audiences/query-audiences-step4-02-summary.png" alt="對象啟用總覽"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="../use-cases/query-audiences.md" title="對象啟用總覽">對象啟用一覽</a>
                    </p>
                    <p class="is-size-6">無須導覽Real-Time CDP，即可檢視哪些對象已上線、流量在哪裡，以及目的地是否健康。</p>
                </div>
                <a href="../use-cases/query-audiences.md" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">檢查對象啟用</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Develop AEM components with AI">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/ai/ai-assisted-development/use-cases/component-development" title="使用AI開發AEM元件" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../assets/agent-skills-card.png" alt="使用AI開發AEM元件"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/ai/ai-assisted-development/use-cases/component-development" target="_blank" rel="referrer" title="使用AI開發AEM元件">使用AI開發AEM元件</a>
                    </p>
                    <p class="is-size-6">使用具備代理程式技能的Claude程式碼或Cursor ，在Adobe最佳實務的指引下，搭配、編碼和調整AEM元件。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/ai/ai-assisted-development/use-cases/component-development" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">嘗試使用代理程式技能</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Invoke AEM APIs from a web app">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/aem-apis/openapis/invoke-api-using-oauth-web-app" title="從網頁應用程式叫用AEM API" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../assets/using-api-card.png" alt="從網頁應用程式叫用AEM API"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        從網頁應用程式<a href="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/aem-apis/openapis/invoke-api-using-oauth-web-app" target="_blank" rel="referrer" title="從網頁應用程式叫用AEM API">叫用AEM API</a>
                    </p>
                    <p class="is-size-6">建立可驗證使用者的網頁應用程式，並使用OAuth呼叫AEM OpenAPIs，以提供控管的程式化存取。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/aem-apis/openapis/invoke-api-using-oauth-web-app" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">嘗試使用API</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

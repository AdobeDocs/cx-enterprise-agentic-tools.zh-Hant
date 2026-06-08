---
title: MCP伺服器
description: 使用模型內容通訊協定伺服器，將任何與MCP相容的AI使用者端連線至Adobe CX Enterprise工作流程。
index: false
source-git-commit: 63f5958eaa227ea21fa5b193a2ac76a69fd349cb
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 2%

---


# MCP伺服器

<!-- last-modified: 2026-05-19 -->

>[!VIDEO](https://video.tv.adobe.com/v/3491320/?learn=on&enablevpops)

Adobe CX Enterprise MCP伺服器可讓任何相容的AI使用者端直接受控存取Adobe資料和工作流程。 連線一次，您就可以查詢行銷活動績效、啟用對象、檢閱歷程、管理內容等，這一切都以淺顯的語言完成，無需離開您的AI環境。 由於MCP伺服器位於AI使用者端和Adobe的基本系統之間，因此您可以在組織的存取控制和資料控管保持有效的同時，獲得自然語言的靈活性。

Adobe MCP伺服器會遵循開啟的模型內容通訊協定標準。 任何與MCP相容的AI使用者端都會連線至任何Adobe MCP伺服器。

## CX Enterprise MCP閘道

![CX Enterprise MCP Gateway可跨完整的Adobe CX Enterprise套裝將AI使用者端連線至MCP工具](../assets/mcp-gateway-hero.gif)

**一個端點。 每個Adobe CX Enterprise MCP伺服器。**

CX企業閘道將您的AI使用者端路由到跨Analytics、行銷活動、內容和資料的工具，而不需要每個應用程式的個別連線。 連線一次，閘道就會根據您的Adobe許可權，僅顯示貴組織有權使用的工具。

>[!BEGINTABS]

>[!TAB CX Enterprise應用程式]

根據您組織的Adobe授權，可使用每個應用程式的工具。

| 應用程式 | 您可以做什麼 |
| --- | --- |
| Adobe Journey Optimizer | [檢閱歷程、行銷活動和頻道設定](https://developer.adobe.com/ai-registry/#/mcp/ajo-mcp-server) |
| Customer Journey Analytics | [查詢報告、探索資料檢視、作者工作區](https://developer.adobe.com/ai-registry/#/mcp/cja-mcp) |
| Real-Time CDP | [檢查目的地、啟用狀態和資料流健康狀態](https://experienceleague.adobe.com/zh-hant/docs/experience-cloud-ai/experience-cloud-ai/mcp/rtcdp-mcp) （已關閉測試版） |

>[!TAB 連線]

無論您要在哪裡使用應用程式特定的MCP端點，都可使用CX Enterprise Gateway端點。

```
https://cx-enterprise.adobe.io/mcp
```

>[!NOTE]
>對於AEM，請使用直接AEM端點 — AEM不會透過CX Enterprise MCP Gateway路由。

出現提示時，請使用您的Adobe ID登入，並選取連結至您的Adobe應用程式的IMS組織。 選擇錯誤的組織是遺失工具或驗證錯誤最常見的來源。

如需完整的設定指示，請參閱下方的[連線到您的AI使用者端](#connect-to-your-ai-client)。

>[!ENDTABS]

## Adobe CX Enterprise MCP伺服器

下列伺服器直接連線，不會透過CX Enterprise MCP Gateway路由。 若要存取AJO、Customer Journey Analytics和Real-Time CDP，請使用上述[CX Enterprise MCP Gateway](#cx-enterprise-mcp-gateway)。

<!--
CARDS

* #cx-enterprise-mcp-gateway
  {title = CX Enterprise MCP Gateway}
  {description = One connection to AJO, CJA, and Real-Time CDP tools. The gateway surfaces only the tools your organization is licensed for.}
  {cta = Connect}
  {image = ../assets/mcp-cxenterprise-card.png}

* https://developer.adobe.com/analytics-mcp/docs/aa/
  {title = Adobe Analytics}
  {description = Tools for report suite discovery, dimension and metric analysis, segment authoring, and workspace creation in Adobe Analytics.}
  {cta = View documentation}
  {target = _blank}
  {image = ../assets/mcp-analytics-card.png}

* https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/ai-in-aem/using-mcp-with-aem-as-a-cloud-service
  {title = AEM Content}
  {description = Tools for managing pages, content fragments, assets, and launches in Adobe Experience Manager as a Cloud Service using natural language.}
  {cta = View documentation}
  {target = _blank}
  {image = ../assets/mcp-aem-card.png}

* https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/ai-in-aem/using-mcp-with-aem-as-a-cloud-service
  {title = AEM Content (Read-Only)}
  {description = Tools for discovering and querying pages, content fragments, and launches in AEM as a Cloud Service. No write access.}
  {cta = View documentation}
  {target = _blank}
  {image = ../assets/mcp-aem-card.png}

* https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/ai/mcp-servers/cloud-manager
  {title = AEM Cloud Manager}
  {description = Tools for managing Cloud Manager programs, environments, pipelines, and repositories from your IDE using natural language.}
  {cta = View documentation}
  {target = _blank}
  {image = ../assets/mcp-aem-card.png}

-->

### MCP伺服器端點

| 伺服器 | 端點 | 工具 |
| --- | --- | --- |
| [CX Enterprise MCP閘道](#cx-enterprise-mcp-gateway) | `https://cx-enterprise.adobe.io/mcp` | · [Adobe Journey Optimizer工具](https://developer.adobe.com/ai-registry/#/mcp/ajo-mcp-server)<br>· [Customer Journey Analytics工具](https://developer.adobe.com/ai-registry/#/mcp/cja-mcp)<br>· [Real-Time CDP工具](https://experienceleague.adobe.com/zh-hant/docs/experience-cloud-ai/experience-cloud-ai/mcp/rtcdp-mcp) |
| [Adobe Analytics](https://developer.adobe.com/analytics-mcp/docs/aa/) | `https://aa-mcp.adobe.io/mcp` | [檢視工具](https://developer.adobe.com/ai-registry/#/mcp/adobe-analytics-mcp) |
| [AEM Cloud Manager](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/ai/mcp-servers/cloud-manager) | `https://mcp.adobeaemcloud.com/adobe/mcp/cloudmanager` | [檢視工具](https://developer.adobe.com/ai-registry/#/mcp/aem-cloud-manager-mcp) |
| [AEM內容](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/ai-in-aem/using-mcp-with-aem-as-a-cloud-service) | `https://mcp.adobeaemcloud.com/adobe/mcp/content` | [檢視工具](https://developer.adobe.com/ai-registry/#/mcp/aem-content-mcp) |
| [AEM內容（唯讀）](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/ai-in-aem/using-mcp-with-aem-as-a-cloud-service) | `https://mcp.adobeaemcloud.com/adobe/mcp/content-readonly` | [檢視工具](https://developer.adobe.com/ai-registry/#/mcp/aem-content-mcp-readonly) |

## 連線至您的AI使用者端

所有Adobe MCP伺服器都使用OAuth搭配Adobe Identity Management服務(IMS)。 出現提示時，請選取正確的IMS組織。 選擇錯誤是驗證錯誤最常見的來源。

在手動設定之前，請檢查[Adobe AI登入](https://developer.adobe.com/ai-registry/?type=connector)，以取得您的AI使用者端和Adobe應用程式的Managed聯結器。 受管理的聯結器會自動處理驗證。 如果您的使用者端和應用程式有可用的聯結器，請改用它，而不是下面的手動步驟。

![連線到Adobe MCP伺服器的AI代理程式](../assets/hero-connect-mcp-servers.gif)

>[!BEGINTABS]

>[!TAB Claude.ai]

### ![建議](../assets/badge-recommended.svg)使用Managed聯結器

移至[Adobe AI登入](https://developer.adobe.com/ai-registry/?type=connector)並搜尋您的Adobe應用程式。 如果列出了Claude聯結器（例如[Adobe Experience Manager聯結器](https://developer.adobe.com/ai-registry/#/connectors/adobe-experience-manager-connector)），請依照其設定指示操作，而非依照下列步驟操作。

### 使用自訂聯結器連線

Claude.ai透過帳戶設定中的自訂聯結器支援遠端MCP伺服器。

1. 移至&#x200B;**設定>整合**。
2. 按一下&#x200B;**新增自訂聯結器**。
3. 輸入`https://cx-enterprise.adobe.io/mcp`作為URL和顯示名稱，例如`Adobe CX Enterprise`。
4. 按一下「**連線**」並使用您的Adobe ID登入。 選取正確的IMS組織。

完整設定： [Claude.ai自訂聯結器檔案](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp)

>[!TAB 克勞德程式碼]

### 使用CLI

執行`claude mcp add`以註冊CX Enterprise MCP閘道。 一個連線可讓您根據組織的授權存取AJO、CJA和Real-Time CDP工具。

```bash
claude mcp add --transport http adobe-cx-enterprise https://cx-enterprise.adobe.io/mcp
```

### 編輯您的設定檔案

將伺服器新增至專案根目錄（專案層級）中的`~/.claude.json` （全域）或`.mcp.json`：

```json
{
  "mcpServers": {
    "adobe-cx-enterprise": {
      "type": "http",
      "url": "https://cx-enterprise.adobe.io/mcp"
    }
  }
}
```

Adobe MCP伺服器使用OAuth。 當您第一次呼叫工具時，克勞德程式碼會提示您使用Adobe ID進行驗證。 出現提示時，請選取正確的IMS組織。

完整設定： [克勞德程式碼MCP檔案](https://docs.anthropic.com/en/docs/claude-code/mcp)

>[!TAB 游標]

將CX Enterprise MCP Gateway加入您的Cursor `mcp.json`組態檔，然後透過&#x200B;**設定> MCP**&#x200B;連線。

- **全域（所有專案）：** `~/.cursor/mcp.json`
- **專案層級：** `.cursor/mcp.json`在您的專案根目錄中

```json
{
  "mcpServers": {
    "adobe-cx-enterprise": {
      "type": "http",
      "url": "https://cx-enterprise.adobe.io/mcp"
    }
  }
}
```

一個閘道專案可讓您根據組織的授權存取AJO、CJA和Real-Time CDP。

新增後，MCP伺服器會出現在游標設定中的&#x200B;**已安裝MCP伺服器**&#x200B;下。 選取任何顯示&#x200B;**需要驗證**&#x200B;且使用您的Adobe ID登入的伺服器旁的&#x200B;**連線**。 選取可存取應用程式的IMS組織。

![Cursor MCP伺服器組態顯示已安裝的Adobe MCP伺服器和mcp.json](../assets/screenshots/cursor-mcp-server-configuration.jpg)

完整設定： [Cursor MCP檔案](https://cursor.com/docs/mcp)

>[!TAB ChatGPT]

### ![建議](../assets/badge-recommended.svg)使用Managed聯結器

移至[Adobe AI登入](https://developer.adobe.com/ai-registry/?type=connector)並搜尋您的Adobe應用程式。 如果列出ChatGPT聯結器，請按照其設定指示操作，而不是下面的步驟。

### 使用遠端MCP伺服器連線

ChatGPT透過Pro、Plus、Business、Enterprise和Education計畫提供的[開發人員模式](https://developers.openai.com/api/docs/guides/developer-mode)支援遠端MCP伺服器。

1. 在&#x200B;**ChatGPT設定**&#x200B;中啟用開發人員模式。
2. 移至&#x200B;**設定>整合**。
3. 按一下&#x200B;**新增自訂聯結器**&#x200B;並選擇&#x200B;**遠端MCP伺服器**。
4. 輸入`https://cx-enterprise.adobe.io/mcp`作為URL，輸入`Adobe CX Enterprise`作為名稱。
5. 將驗證設定為&#x200B;**OAuth**。
6. 按一下「**連線**」並使用您的Adobe ID登入。 選取正確的IMS組織。

完整設定： [ChatGPT MCP檔案](https://developers.openai.com/api/docs/guides/tools-connectors-mcp)

>[!TAB OpenAI程式碼CLI]

OpenAI Codex CLI透過TOML組態支援遠端MCP伺服器。

**設定檔位置：**

- **使用者層級（所有專案）：** `~/.codex/config.toml`
- 專案根目錄中的&#x200B;**專案範圍：** `.codex/config.toml`

新增CX Enterprise MCP Gateway：

```toml
[mcp_servers.adobe-cx-enterprise]
url = "https://cx-enterprise.adobe.io/mcp"
enabled = true
```

Adobe MCP伺服器使用OAuth。 Codex CLI會在第一次使用時自動處理OAuth流程。 出現提示時，請選取正確的IMS組織。

完整設定： [OpenAI Codex CLI MCP檔案](https://developers.openai.com/codex/mcp)

>[!TAB Copilot Studio]

Microsoft Copilot Studio使用MCP上線精靈連線到遠端MCP伺服器，精靈會自動建立Power Platform自訂聯結器。

1. 在Copilot Studio中開啟代理程式。
2. 移至&#x200B;**工具**&#x200B;頁面。
3. 選取&#x200B;**新增工具>新增工具>模型內容通訊協定**。
4. 在MCP上線精靈中，輸入：
   - **伺服器名稱：** `Adobe CX Enterprise`
   - **伺服器URL：** `https://cx-enterprise.adobe.io/mcp`
5. 將驗證設定為&#x200B;**OAuth 2.0**，並使用您的Adobe IMS授權和權杖URL進行設定。
6. 選取&#x200B;**建立**，然後選取&#x200B;**新增至代理程式**。

>[!NOTE]
>
>Copilot Studio中的MCP伺服器連線會通過Power Platform。 您組織的資料遺失預防(DLP)政策在此適用。

完整設定： [Copilot Studio MCP檔案](https://learn.microsoft.com/microsoft-copilot-studio/mcp-add-existing-server-to-agent)

>[!ENDTABS]

## 疑難排解

+++切換Adobe組織

如果您的Adobe使用者屬於多個IMS組織，而您看到錯誤的工具或資料，請中斷MCP伺服器連線，在瀏覽器中登出Adobe工作階段，然後重新連線。 登入時，系統會提示您選擇組織。

Adobe CX Enterprise MCP伺服器一次只能驗證一個IMS組織，即使您的使用者帳戶可存取多個組織亦然。

+++

+++指定沙箱、報告套裝、環境或其他工作階段資源

有些Adobe CX Enterprise MCP伺服器需要您指定資源，才能傳回結果。 根據應用程式的不同，這可能是沙箱、程式、環境、報表套裝或資料檢視。

如果您不確定您有權存取哪些資源，請向AI使用者端詢問。 例如：「列出可用的沙箱」或「我有權存取哪些報表套裝？」 Adobe CX Enterprise MCP伺服器通常會傳回使用者可用的完整資源清單。

設定工作階段資源後，您可以隨時通知AI使用者端要使用哪個工作階段資源，以進行切換。

+++

+++許可權和存取錯誤

AI使用者端使用OAuth來代表您的Adobe使用者帳戶行事。 當您登入Adobe應用程式時，所套用的許可權和存取控制也會在您使用MCP伺服器時套用。

如果動作失敗或未傳回任何結果，請檢查您的使用者是否在Adobe Admin Console和相關CX Enterprise應用程式中擁有所需許可權。 如果您需要調整存取許可權，請聯絡您的Adobe系統管理員。

+++

+++在遺失工作階段後重新驗證

Adobe CX Enterprise MCP伺服器會使用OAuth驗證您的Adobe使用者帳戶。 如果驗證狀態遺失，在您重新驗證之前，將不會成功進行進一步的工具呼叫。

若要重新驗證：開啟您的AI使用者端的MCP伺服器設定，選取Adobe CX Enterprise MCP伺服器專案，然後重新連線。 系統會提示您再次使用Adobe ID登入。

+++

## 執行中的代理工具

請參閱套用至實際業務工作流程的Adobe CX Enterprise MCP伺服器。

<!--
CARDS

* ../use-cases/analyze-campaign-performance.md
  {title = Analyze campaign performance}
  {description = Use the CX Enterprise MCP Gateway to surface Customer Journey Analytics metrics and insights from any AI client.}
  {cta = Start walkthrough}

* ../use-cases/query-audiences.md
  {title = Query audiences}
  {description = Use the CX Enterprise MCP Gateway to query Real-Time CDP audience and destination data using plain language prompts.}
  {cta = Start walkthrough}

* ../use-cases/manage-ajo-journeys.md
  {title = Review AJO journeys}
  {description = Use the CX Enterprise MCP Gateway to access AJO journeys, campaign status, and journey conditions from your AI client.}
  {cta = Start walkthrough}

* ../use-cases/manage-aem-content.md
  {title = Manage AEM content with AI}
  {description = Discover, update, and publish pages and content fragments in AEM using natural language.}
  {cta = Start walkthrough}

* ../use-cases/optimize-content-with-performance-data.md
  {title = Optimize content based on performance data}
  {description = Combine the CX Enterprise MCP Gateway and AEM Content MCP Server to find underperforming content and update it in one session.}
  {cta = Start walkthrough}

* ../use-cases/cross-channel-campaign-review.md
  {title = Run a cross-channel campaign review}
  {description = Use the CX Enterprise MCP Gateway for a unified view of AJO, CJA, and Real-Time CDP campaign health in one AI session.}
  {cta = Start walkthrough}
-->

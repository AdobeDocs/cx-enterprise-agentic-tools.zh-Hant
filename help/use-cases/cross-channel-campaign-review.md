---
title: 執行跨頻道行銷活動審查
description: 在單一AI工作階段中使用CX Enterprise MCP，即可跨歷程、對象和效能統一檢視AJO、CJA和Real-Time CDP行銷活動健康情況。
last-substantial-update: 2026-06-09T00:00:00Z
index: false
source-git-commit: 6a2b8b54eb9fe040f5f9defa9e6681e46a5e65cf
workflow-type: tm+mt
source-wordcount: '1412'
ht-degree: 5%

---


# 執行跨頻道行銷活動審查

<!-- last-modified: 2026-05-21 -->

![執行跨頻道行銷活動評論](https://placehold.co/1600x900?text=Cross-Channel+Campaign+Review)

全面掌握行銷活動健康情況需要來自多個系統的資料：來自AJO的活動歷程、來自Real-Time CDP的受眾啟用狀態，以及來自CJA的績效量度。 此逐步解說會說明如何在單一AI工作階段中連線所有三個，讓您能夠在一個交談中（而不是三個單獨的工具）從歷程狀態到受眾健康狀態再到效能趨勢。

| 案例詳細資料 | |
| --- | --- |
| CX企業應用程式 | [Adobe Journey Optimizer](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home)，[Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-overview)，[Real-Time CDP](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/rtcdp/home) |
| 代理工具 | [CX Enterprise MCP](../tools/mcp-servers.md#cx-enterprise-mcp-servers) |
| 對象 | 行銷活動經理，行銷作業 |
| 先決條件 | MCP相容的AI使用者端、AJO、CJA和Real-Time CDP的存取權 |

每個步驟會顯示一個代表性提示和範例AI回應。 您可以完成更多&#x200B;**個**&#x200B;區段，在同一工作階段中進行更多探索。

## 開始之前

>[!BEGINTABS]

>[!TAB Claude.ai]

將CX Enterprise MCP連線為自訂聯結器。 一個連線可讓您存取AJO、CJA和Real-Time CDP工具。

1. 移至Claude.ai中的&#x200B;**設定>整合**。
2. 選取&#x200B;**新增自訂聯結器**&#x200B;並輸入伺服器URL： `https://cx-enterprise.adobe.io/mcp`
3. 選取&#x200B;**連線**&#x200B;並使用您的Adobe ID登入。

完整設定： [Claude.ai自訂聯結器檔案](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp)

>[!TAB ChatGPT]

使用ChatGPT Developer Mode連線CX Enterprise MCP （需要Pro、Plus、Business、Enterprise或Education計畫）。

1. 在&#x200B;**ChatGPT設定**&#x200B;中啟用&#x200B;**開發人員模式**。
2. 移至&#x200B;**設定>整合**&#x200B;並選取&#x200B;**新增自訂聯結器>遠端MCP伺服器**。
3. 輸入伺服器URL： `https://cx-enterprise.adobe.io/mcp`
4. 選取&#x200B;**連線**&#x200B;並使用您的Adobe ID登入。

完整設定： [ChatGPT MCP檔案](https://developers.openai.com/api/docs/guides/tools-connectors-mcp)

>[!TAB 其他AI使用者端]

使用Gemini、Microsoft Copilot、Cursor、Claude Code或其他與MCP相容的環境嗎？ 使用此端點連線到CX Enterprise MCP：

```
https://cx-enterprise.adobe.io/mcp
```

所有支援使用者端的完整設定指示： [連線到您的AI使用者端](../tools/mcp-servers.md)

>[!ENDTABS]

>[!NOTE]
>
>出現提示時，請使用您的Adobe ID登入，然後選取連結至您的AJO、CJA和Real-Time CDP環境的IMS組織。 選擇錯誤的組織是驗證錯誤最常見的來源。
>
>在首次連線時，您的AI使用者端可能會要求您選取IMS組織或指定沙箱。 設定該內容後，MCP伺服器會將其用於工作階段的其餘部分。
>
>有些工具在執行前會提示您核准。 檢閱請求並核准或拒絕。 未經您的確認，不會採取任何動作。

## 步驟1：檢閱作用中的歷程與行銷活動

從AJO開始，建立目前執行的專案。 瞭解哪些歷程為即時狀態且最近修改過，是進行其餘評論的基礎。

```
What journeys are currently active in AJO?
```

+++檢視範例回應

在您的AJO組織中找到8個使用中的歷程：

| 歷程 | 管道 | 上次修改時間 |
| --- | --- | --- |
| 歡迎系列：新成員 | 電子郵件、推播 | 2026年5月18日 |
| 購買後追蹤 | 電子郵件、簡訊 | 2026年5月14日 |
| 再次參與忠誠度 | 電子郵件 | 2026年5月20日 |
| 捨棄的購物車：24小時 | 電子郵件、簡訊 | 2026年5月10日 |
| Spring Promotion | 電子郵件、推播 | 2026年5月19日 |
| 回合：90天非使用中 | 電子郵件 | 2026年4月28日 |
| 生日獎勵 | 電子郵件 | 2026年4月15日 |
| 重新參與：推播選擇退出 | 簡訊 | 2026年5月12日 |

過去7天內修改了3個歷程。 您想要瞭解其中任何專案的詳細資訊嗎？

+++


## 步驟2：檢查對象啟用狀態

檢視歷程時，請確認為這些行銷活動提供支援的受眾是否正確流向其目的地。

```
Show me the activation status for the high-value loyalty segment.
```

+++檢視範例回應

**高價值忠誠度區段**：各個目的地的啟用狀態：

| 目標 | 狀態 | 上一次成功的執行 | 對象規模 |
| --- | --- | --- | --- |
| Google Ads | 作用中 | 2026年5月21日凌晨02:14 | 48,320 |
| Meta Ads | 作用中 | 2026年5月21日上午01:58 | 48,295 |
| Salesforce Marketing Cloud | 作用中 | 2026年5月20日晚上11:30 | 47,940 |
| Adobe Target | 作用中 | 2026年5月21日上午12:00 | 48,320 |

未偵測到任何資料流錯誤。 所有啟用在過去3小時內完成。

+++


## 步驟3：從CJA提取績效量度

建立歷程和受眾內容後，使用CJA評估這些行銷活動的轉換方式以及參與度下降的位置。

```
Show me click-through and conversion rates for the [campaign name] campaign over the last 30 days.
Show me click-through and conversion rates for the [campaign name] campaign over the last 30 days.
```

+++檢視範例回應

**忠誠度重新參與行銷活動**： 2026年4月21日至5月21日：

| 頻道 | 傳送 | CTR | 轉換 | 同意 比率 |
| --- | --- | --- | --- | --- |
| 電子郵件 | 48,320 | 8.4% | 1,973 | 4.1% |
| 推播 | 31,200 | 12.1% | 987 | 3.2% |

合併轉換率：3.8%。 電子郵件CTR較之前30天期間上升1.2%。 推播轉換平穩。

+++


## 步驟4：綜合行銷活動健康情況摘要

請您的AI使用者端將這三個來源的圖片彙整在一起，並呈現任何需要注意的東西。

```
Give me a summary of our campaign health: what is running, which audiences are activated, and how performance looks against last month.
```

+++檢視範例回應

以下是您目前在AJO、Real-Time CDP和CJA中的行銷活動健康情況摘要：

**使用中的歷程：** 8個即時，3個本週修改。 忠誠度重新參與歷程是最近更新的。

**對象啟用：**&#x200B;所有區段都正確流動到4個目的地。 未偵測到任何資料流錯誤。

**績效：**&#x200B;忠誠度行銷活動的電子郵件CTR為使用中。 推播轉換持平。 沒有管道明顯下降。

**要注意的旗標：**

- 贏回歷程（90天非使用中）上次修改於23天前，最近未經過稽核。
- 推播轉換率連續3個期間保持不變，值得檢閱訊息或時機。

未偵測到任何嚴重問題。 上述兩個專案值得在下次行銷活動啟動前檢閱。

+++


多伺服器方法從中取得成效：在單一交談中，跨越歷程設定、對象狀態和效能資料的AI使用者端原因。

## 步驟5：對找到的專案採取動作

稽核顯示兩個專案。 請要求您的AI使用者端協助您排定每個專案的優先順序並進行路由。

```
For each flag you identified, what should I do and where should I go to do it?
```

+++檢視範例回應

以下是兩種旗幟的優先行動計畫：

**1. Win-Back journey — 檢閱重新進入條件（AJO MCP，如果需要變更，則檢閱AJO應用程式）**

已有23天未修改回溯歷程。 要求我逐步瞭解其目前的重新進入條件和退出邏輯。 如果條件看起來陳舊或不正確，對歷程流程的結構變更需要開啟AJO。 頻率上限和對象更新可在此處進行。

**2. 3個期間的平面推播轉換 — 更新傳訊或測試變體**

一般轉換通常表示訊息疲勞或選件和對象之間的不相符。 兩個路徑：

- **立即更新推播內容(AEM MCP)：**&#x200B;如果推播通知連結至登陸頁面，請新增AEM Content MCP Server並更新頁面副本或CTA，而不需切換工具。
- **執行推播A/B測試（AJO應用程式）：**&#x200B;建立具有不同訊息的行銷活動層級變體，以隔離該變體是內容還是目標。 需要直接前往AJO。

您想要從哪個開始？

+++


## 您完成的內容

您已將AJO、Real-Time CDP和CJA連結至單一AI工作階段，執行跨頻道行銷活動健康情況審查。 您不是在開啟三個應用程式並手動組合像片，而是在一次交談中瀏覽歷程狀態、對象啟用和效能資料。 綜合摘要可讓行銷活動經理更快速地找出有效專案、需要調整的專案以及下一步要著重在何處。

## 您可以完成更多工作

透過在同一工作階段中連結AJO、CJA和Real-Time CDP，您可以超越逐步解說。 展開下面的案例以檢視您可以嘗試的提示。

+++在啟動新功能之前，請先確切瞭解正在執行的動作

重疊的歷程、最近修改的行銷活動，以及您未檢閱的管道，都可能會影響新的啟動。 在您新增任何專案之前，這些提示會提供您目前狀態的清楚圖片。

**提示**

```
Which journey has the most active profiles right now?
```

```
Show me all journeys modified in the last 7 days.
```

```
Which campaigns are scheduled to end this week?
```

```
Are any journeys targeting the same segment as the campaign I'm about to launch?
```

+++

+++確定對象已到達正確的目的地

啟用問題無訊息 — 區段停止流動，您的行銷活動會傳送至較小的清單，而不會出現任何警告。 這些會在曲面間隙和錯誤影響結果之前提示它們。

**提示**

```
Which audiences have grown the most in the last 30 days?
```

```
Are there any dataflow errors across my active destinations?
```

```
How many records were exported to each destination in the last 7 days?
```

```
Are there any audiences with no active destinations?
```

+++

+++瞭解目前發揮作用的因素以及下一步應該聚焦在何處

各管道的效能趨勢可告訴您應在何處投資以及應該從何處撤回。 這些提示可協助您識別促成結果的因素，以及下一季的注意力應流向何處。

**提示**

```
Show me email performance trends for the last 90 days.
```

```
Which campaigns are underperforming against their conversion targets?
```

```
What is the average revenue per conversion this month compared to last month?
```

```
Which channel has the highest conversion rate across all active campaigns?
```

+++


## 進一步資訊

| 資源 | 您會找到的內容 |
| --- | --- |
| [AJO檔案](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"} | 完整的AJO應用程式檔案 |
| AI登入中的[AJO MCP伺服器](https://developer.adobe.com/ai-registry/#/mcp/ajo-mcp-server){target="_blank"} | AJO MCP伺服器工具與可用性 |
| AI登入中的[CJA MCP伺服器](https://developer.adobe.com/ai-registry/#/mcp/cja-mcp){target="_blank"} | CJA MCP伺服器工具與可用性 |

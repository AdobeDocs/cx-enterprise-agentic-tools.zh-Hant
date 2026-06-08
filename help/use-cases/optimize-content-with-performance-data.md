---
title: 根據效能資料最佳化內容
description: 將CJA和AEM MCP伺服器搭配使用，找出表現缺佳的內容並加以更新，無需在工具之間切換。
index: false
source-git-commit: 63f5958eaa227ea21fa5b193a2ac76a69fd349cb
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 3%

---


# 根據效能資料最佳化內容

<!-- last-modified: 2026-05-21 -->

![根據效能資料最佳化內容](https://placehold.co/1600x900?text=Optimize+Content+Based+on+Performance+Data)

關閉內容效能資料和內容更新之間的回圈，通常表示在Analytics和CMS之間切換。 本逐步解說會說明如何在相同的AI工作階段中連結Customer Journey Analytics和AEM，以便您可以在不離開交談的情況下顯示表現缺佳的頁面並進行更新。

| | |
| --- | --- |
| CX企業應用程式 | Customer Journey Analytics、Adobe Experience Manager as a Cloud Service |
| 代理工具 | CX Enterprise MCP Gateway、AEM Content MCP Server |
| 客群 | 行銷活動經理、內容策略師、行銷作業 |
| 先決條件 | MCP相容的AI使用者端、CJA存取、AEM as a Cloud Service存取 |

每個步驟會顯示一個代表性提示和範例AI回應。 您可以完成更多&#x200B;**個**&#x200B;區段，在同一工作階段中進行更多探索。

## 開始之前

>[!BEGINTABS]

>[!TAB Claude.ai]

將兩個MCP伺服器連線為自訂聯結器。 分別新增各個。

1. 移至Claude.ai中的&#x200B;**設定>整合**。
2. 選取&#x200B;**新增自訂聯結器**，輸入伺服器URL，然後選取&#x200B;**連線**。
3. 使用您的Adobe ID登入，然後為第二個伺服器重複此程式。

| 伺服器 | 端點 |
| --- | --- |
| CX Enterprise MCP閘道 | `https://cx-enterprise.adobe.io/mcp` |
| AEM Content MCP Server | `https://mcp.adobeaemcloud.com/adobe/mcp/content` |

完整設定： [Claude.ai自訂聯結器檔案](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp)

>[!TAB ChatGPT]

使用ChatGPT Developer Mode （Pro、Plus、Business、Enterprise或Education plan required）連線兩部MCP伺服器。 分別新增每個伺服器。

1. 在&#x200B;**ChatGPT設定**&#x200B;中啟用&#x200B;**開發人員模式**。
2. 移至&#x200B;**設定>整合**&#x200B;並選取&#x200B;**新增自訂聯結器>遠端MCP伺服器**。
3. 輸入伺服器URL，選取&#x200B;**連線**，然後使用您的Adobe ID登入。
4. 對第二個伺服器重複此動作。

| 伺服器 | 端點 |
| --- | --- |
| CX Enterprise MCP閘道 | `https://cx-enterprise.adobe.io/mcp` |
| AEM Content MCP Server | `https://mcp.adobeaemcloud.com/adobe/mcp/content` |

完整設定： [ChatGPT MCP檔案](https://developers.openai.com/api/docs/guides/tools-connectors-mcp)

>[!TAB 其他AI使用者端]

使用Gemini、Microsoft Copilot、Cursor、Claude Code或其他與MCP相容的環境嗎？ 使用下列端點連線到兩個MCP伺服器：

| 伺服器 | 端點 |
| --- | --- |
| CX Enterprise MCP閘道 | `https://cx-enterprise.adobe.io/mcp` |
| AEM Content MCP Server | `https://mcp.adobeaemcloud.com/adobe/mcp/content` |

所有支援使用者端的完整設定指示： [連線到您的AI使用者端](../tools/mcp-servers.md)

>[!ENDTABS]

>[!NOTE]
>
>出現提示時，請使用您的Adobe ID登入，然後選取連結至您的CJA和AEM環境的IMS組織。 選擇錯誤的組織是驗證錯誤最常見的來源。
>
>在首次連線時，您的AI使用者端可能會要求您選取IMS組織或指定沙箱。 設定該內容後，MCP伺服器會將其用於工作階段的其餘部分。
>
>有些工具在執行前會提示您核准。 檢閱請求並核准或拒絕 — 未經您的確認不會採取任何動作。

## 步驟1：識別表現不佳的內容

使用CX Enterprise MCP Gateway，在Customer Journey Analytics中依參與和轉換量度來排名頁面。 目標是列出需要注意的清晰、優先順序排定的內容清單。

```
Show me the 10 pages with the lowest engagement rate over the last 60 days.
```

+++檢視範例回應

最低參與頁面（2026年3月22日至5月21日）：

| 排名 | 頁面 | 參與率 | 退回率 | 平均 頁面逗留時間 |
| --- | --- | --- | --- | --- |
| 1 | /en/products/analytics | 8.2% | 74% | 0:42 |
| 2 | /en/resources/whitepapers | 9.1% | 71% | 0:38 |
| 3 | /en/solutions/retail | 10.4% | 69% | 0:51 |
| 4 | /en/blog/2025-q4-recap | 11.0% | 68% | 0:44 |
| 5-10 | ... | 12.3-14.1% | 63-67% | 0:35-1:10 |

您的網站平均參與率為34.7%。 這些頁面比平均水準低2-4倍。

+++

## 步驟2：檢閱AEM中的內容

在不離開您的AI工作階段的情況下，從AEM提取這些頁面的目前狀態。 瞭解內容的含義是瞭解要變更內容的第一步。

```
Show me the current content on the /en/products/analytics page in AEM.
```

+++檢視範例回應

**頁面：** `/en/products/analytics`
**上次修改日期：** 2026年4月30日，T. MacMillan
**狀態：**&#x200B;已發佈

**主圖區段：**
Headline： 「每個團隊的資料導向式決策」
Subheadline： 「Adobe Analytics讓您的組織具備行動所需的深入解析。」
CTA： /contact/demo→的「要求示範」

**內文：** 3個功能區塊，後面接著客戶標誌帶和次要CTA。 沒有視訊或互動式元素。 21天未更新頁面。

**Meta說明：** 「Adobe Analytics：企業團隊的即時報表和AI深入分析」。

+++

## 步驟3：進行目標式更新

檢視效能資料和目前內容後，根據資料所顯示的內容進行更新。

```
Update the hero headline on the analytics product page to Make faster decisions with AI-powered analytics.
```

+++檢視範例回應

**提議的變更：**

| 欄位 | 目前值 | 新值 |
| --- | --- | --- |
| 英雄標題 | 每個團隊的資料導向式決策 | 利用AI支援的分析更快決策 |

頁面： `/en/products/analytics`

確認此變更？ 回覆「是」會將更新寫入AEM。 在您明確重新發佈之前，頁面將保持其目前狀態。

+++

>[!CAUTION]
>
>出現提示時確認每個內容變更。 在核准即時頁面的更新之前，請檢閱完整的差異。

## 步驟4：驗證並發佈

當您對更新感到滿意時，確認所有變更並提升內容以關閉回圈。

```
Show me a summary of all changes made in this session.
```

+++檢視範例回應

**工作階段摘要 — 2026年5月21日：**

| 頁面 | 變更 | 狀態 |
| --- | --- | --- |
| /en/products/analytics | 英雄標題已更新 | 已儲存，已取消發佈 |

已更新1頁。 確認後可發佈。

**您低參與清單中的剩餘專案：** 9頁尚未在此工作階段中更新。 您要繼續下一頁，還是要建立啟動項，以便在發佈前進行批次檢閱？

+++

## 您完成的內容

您在單一AI工作階段中連線Customer Journey Analytics和AEM，並使用效能資料直接通知內容變更。 您在不切換工具的情況下從量度移至更新，縮短了Analytics insight與發佈內容之間的回饋迴路。 這在行銷活動規模上最為重要，因為許多頁面可能需要引起注意，而手動跨工具工作流程會產生延遲。

## 您可以完成更多工作

CJA和AEM MCP伺服器可共同支援從識別問題到送貨修正的完整週期。 展開下列案例以檢視可在相同工作階段中嘗試的提示。

+++尋找阻礙效能的內容

高流量和低參與度表示內容問題，而非流量問題。 這些提示可協助您在行銷活動期限強制問題發生之前顯示需要注意的特定頁面和模式。

**提示**

```
Show me the 10 pages with the lowest conversion rate this quarter.
```

```
Which pages have a high bounce rate but also high traffic?
```

```
Compare engagement rates for blog posts versus product pages.
```

```
Find AEM pages that haven't been updated in over 60 days.
```

+++

+++修正資料告訴您的修正內容

一旦您知道哪些專案表現不佳，下一步就是進行目標性的變更。 這些提示可讓您根據效能資料所顯示的內容，更新標題、CTA和中繼說明。

**提示**

```
Update the CTA on the /en/solutions/retail page to 'See how it works'.
```

```
Add a note to the hero subheadline on the analytics page: Now with AI-powered anomaly detection.
```

```
Update the meta description on all pages in /en/products/ that contain the word 'legacy'.
```

```
Which pages updated in this session still need their CTAs reviewed?
```

+++

+++下次行銷活動前的出貨改善

工作階段期間所做的變更可能會快速累積。 這些提示可協助您稽核就緒的專案、將更新分組在可檢視的啟動中，以及在行銷活動上線之前以簡潔的方式提升。

**提示**

```
Show me all pages updated in this session that are still unpublished.
```

```
Create a launch with all changes from this session for review before publishing.
```

```
Give me a summary of all changes made in this session.
```

```
Promote everything in the current launch to production.
```

+++

## 進一步資訊

| 資源 | 您會找到的內容 |
| --- | --- |
| [Analytics MCP檔案](https://developer.adobe.com/analytics-mcp/docs/) | CJA MCP設定和工具參考 |
| [AEM as a Cloud Service 文件](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service) | 完整的AEM檔案 |
| AI登入中的[CJA MCP伺服器](https://developer.adobe.com/ai-registry/#/mcp/cja-mcp) | CJA MCP伺服器工具與可用性 |
| [AI登入中的AEM Content MCP伺服器](https://developer.adobe.com/ai-registry/#/mcp/aem-content-mcp) | AEM Content MCP Server工具與可用性 |
| [MCP伺服器](../tools/mcp-servers.md) | 將AI使用者端連線至Adobe MCP伺服器 |
